---
layout: default
title: Discret Fourier Transform
parent: References
permalink: /2-references/dft
---

<h1>DFT library reference</h1>

<h2>Table of contents</h2>

<ul class="disc">
  <li><a href="#tutorial">Tutorial</a></li>
  <!--<li><a href="#compatibility">Compatibility with other libraries</a></li>-->
  <li><a href="l#reference">Function reference</a></li>
</ul>

<h2 id="tutorial">Tutorial</h2>

<p class="noindent">
  I now explain how to use this DFT library by referring to an example
  source code shown below. 
  <a class="underlined" href="../../src/tutorial.c">This source code</a> is
  included in the distribution package under src/dft-tester directory.
</p>

<pre class="code">
<code>// gcc tutorial.c -lsleef -lsleefdft -lm</code>
<code>#include &lt;stdio.h&gt;</code>
<code>#include &lt;stdlib.h&gt;</code>
<code>#include &lt;stdint.h&gt;</code>
<code>#include &lt;math.h&gt;</code>
<code>#include &lt;complex.h&gt;</code>
<code></code>
<code>#include "sleef.h"</code>
<code>#include "sleefdft.h"</code>
<code></code>
<code>#define THRES 1e-4</code>
<code></code>
<code>typedef double complex cmpl;</code>
<code></code>
<code>cmpl omega(double n, double kn) {</code>
<code>  return cexp((-2 * M_PI * _Complex_I / n) * kn);</code>
<code>}</code>
<code></code>
<code>void forward(cmpl *ts, cmpl *fs, int len) {</code>
<code>  for(int k=0;k&lt;len;k++) {</code>
<code>    fs[k] = 0;</code>
<code>    for(int n=0;n&lt;len;n++) fs[k] += ts[n] * omega(len, n*k);</code>
<code>  }</code>
<code>}</code>
<code></code>
<code>int main(int argc, char **argv) {</code>
<code>  int n = 256;</code>
<code>  if (argc == 2) n = 1 &lt;&lt; atoi(argv[1]);</code>
<code></code>
<code>  SleefDFT_setPlanFilePath("plan.txt", NULL, SLEEF_PLAN_AUTOMATIC);</code>
<code></code>
<code>  double *sx = (double *)Sleef_malloc(n*2 * sizeof(double));</code>
<code>  double *sy = (double *)Sleef_malloc(n*2 * sizeof(double));</code>
<code></code>
<code>  struct SleefDFT *p = SleefDFT_double_init1d(n, sx, sy, SLEEF_MODE_FORWARD);</code>
<code></code>
<code>  if (p == NULL) {</code>
<code>    printf("SleefDFT initialization failed\n");</code>
<code>    exit(-1);</code>
<code>  }</code>
<code></code>
<code>  cmpl *ts = (cmpl *)malloc(sizeof(cmpl)*n);</code>
<code>  cmpl *fs = (cmpl *)malloc(sizeof(cmpl)*n);</code>
<code></code>
<code>  for(int i=0;i&lt;n;i++) {</code>
<code>    ts[i] =</code>
<code>      (2.0 * (rand() / (double)RAND_MAX) - 1) * 1.0 +</code>
<code>      (2.0 * (rand() / (double)RAND_MAX) - 1) * _Complex_I;</code>
<code></code>
<code>    sx[(i*2+0)] = creal(ts[i]);</code>
<code>    sx[(i*2+1)] = cimag(ts[i]);</code>
<code>  }</code>
<code></code>
<code>  forward(ts, fs, n);</code>
<code></code>
<code>  SleefDFT_double_execute(p, NULL, NULL);</code>
<code></code>
<code>  int success = 1;</code>
<code></code>
<code>  for(int i=0;i&lt;n;i++) {</code>
<code>    if ((fabs(sy[(i*2+0)] - creal(fs[i])) &gt; THRES) ||</code>
<code>        (fabs(sy[(i*2+1)] - cimag(fs[i])) &gt; THRES)) {</code>
<code>      success = 0;</code>
<code>    }</code>
<code>  }</code>
<code></code>
<code>  printf("%s\n", success ? "OK" : "NG");</code>
<code></code>
<code>  free(fs); free(ts);</code>
<code>  Sleef_free(sy); Sleef_free(sx);</code>
<code></code>
<code>  SleefDFT_dispose(p);</code>
<code></code>
<code>  exit(success);</code>
<code>}</code>
</pre>
<p style="text-align:center;">
  Fig. 4.1: <a href="../../src/tutorial.c">Test code for DFT subroutines</a>
</p>

<div style="margin-top: 1.0cm;"></div>

<p>
  As shown in the first line, you can compile the source code with the
  following command, after you install the library.
</p>

<pre class="command">$ gcc tutorial.c -lsleef -lsleefdft -lm
</pre>

<p>
  This program takes one integer argument <i class="var">n</i>. It executes
  forward complex transform with size 2<sup><i class="var">n</i></sup> using a
  naive transform and the library. If the two results match, it prints
  OK.
</p>

<p>
  For the first execution, this program takes a few seconds to
  finish. This is because the library measures computation speed with
  many different configurations to find the best execution plan. The
  best plan is saved to "plan.txt", as specified in line 28. Later
  executions will finish instantly as the library reads the plan from
  this file. Instead of specifying the file name in the program, the
  file can be specified by SLEEFDFTPLAN environment variable. Instead
  of constructing or loading a plan, the library can estimate a
  modestly good configuration, if SLEEF_MODE_ESTIMATE flag is
  specified at line 30.
</p>

<p>
  This library executes transforms using the most suitable SIMD
  instructions available on the computer, in addition to
  multi-threading. In order to make the computation efficient, the
  library requires the input and output arrays to be aligned to some
  boundaries so that the data can be accessed with SIMD
  instructions. By using <b class="func">Sleef_malloc</b>, as seen in
  line 37 and 38, this alignment is ensured. Memory allocated
  with <b class="func">Sleef_malloc</b> has to be freed
  with <b class="func">Sleef_free</b>, as seen in line 68.  When a
  transform is executed, you need to pass the pointer returned
  by <b class="func">Sleef_malloc</b>. You can allocate an aligned
  memory region yourself, and pass the pointer to the library.
</p>

<p>
  The real and imaginary parts of the <i>k</i>th number
  are stored in (2<i>k</i>)-th and
  (2<i>k</i>+1)-th elements of the input and output array,
  respectively. At line 54, the transform is executed by the
  library. You can specify the same array as the input and output.
</p>

<p>
  Under ../src/dft-tester directory, there are other examples showing how
  to execute transforms in a way that you get equivalent results to
  other libraries.
</p>

<!--<h2 id="compatibility">Compatibility with other libraries</h2>-->


<h2 id="reference">Function reference</h2>

<p class="funcname"><b class="func">Sleef_malloc</b> - allocate aligned memory</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;stdlib.h&gt;<br/>
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">void *</b> <b class="func">Sleef_malloc</b>(<b class="type">size_t</b> <i class="var">z</i>);<br/>
<br/>
Link with -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
  <b class="func">Sleef_malloc</b> allocates <i class="var">z</i> bytes of aligned
  memory region, and return the pointer to that region. The returned
  pointer points an address that can be accessed by all SIMD load and
  store instructions available on that computer. Memory regions
  allocated by <b class="func">Sleef_malloc</b> have to be freed
  with <b class="func">Sleef_free</b>.
</p>

<hr/>

<p class="funcname"><b class="func">Sleef_free</b> - free memory allocated by <b class="func">Sleef_malloc</b></p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;stdlib.h&gt;<br/>
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">void</b> <b class="func">Sleef_free</b>(<b class="type">void *</b><i class="var">ptr</i>);<br/>
<br/>
Link with -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
  A memory region pointed by <i class="var">ptr</i> that is allocated
by <b class="func">Sleef_malloc</b> can be freed
with <b class="func">Sleef_free</b>.
</p>

<hr/>

<p class="funcname"><b class="func">SleefDFT_setPlanFilePath</b> - set the file path for storing execution plans</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;stdint.h&gt;<br/>
#include &lt;sleefdft.h&gt;<br/>
<br/>
<b class="type">void</b> <b class="func">SleefDFT_setPlanFilePath</b>(<b class="type">const char *</b><i class="var">path</i>, <b class="type">const char *</b><i class="var">arch</i>, <b class="type">uint64_t</b> <i class="var">mode</i>);<br/>
<br/>
Link with -lsleefdft -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
File name for storing execution plan can be specified by this
function. If NULL is specified as <i class="var">path</i>, the file name is read
from SLEEFDFTPLAN environment variable. A string for identifying
system micro architecture can be also given. The library will
automatically detect the marchitecture if NULL is given
as <i class="var">arch</i>. Management options for the plan file can be specified
by the <i class="var">mode</i> parameter, as shown below.
</p>

<div style="margin-top: 1.0cm;"></div>

<table style="text-align:center;" align="center">
  <tr align="center">
    <td class="caption">Table 4.2: Mode flags for SleefFT_setPlanFilePath</td>
  </tr>
  <tr align="center">
    <td>
      <table class="lt">
        <tr>
          <td class="lt-hl"></td>
          <td class="lt-hl"></td>
        </tr>
	<tr>
	  <td class="lt-br" align="center">Flag</td>
	  <td class="lt-b" align="center">Meaning</td>
	</tr>
	<tr>
	  <td class="lt-hl"></td>
	  <td class="lt-hl"></td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">SLEEF_PLAN_AUTOMATIC</td>
	  <td class="lt-" align="left">Execution plans are automatically loaded and saved. Plans are generated if it does not exist.</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">SLEEF_PLAN_READONLY</td>
	  <td class="lt-" align="left">Execution plans are automatically loaded, but not saved.</td>
	</tr>
	<tr>
	  <td class="lt-br" align="left">SLEEF_PLAN_RESET</td>
	  <td class="lt-b" align="left">Existing execution plans are reset and constructed from the beginning.</td>
	</tr>
      </table>
    </td>
  </tr>
</table>

<hr/>

<p class="funcname"><b class="func">SleefDFT_double_init1d</b>, <b class="func">SleefDFT_float_init1d</b> - initialize the tables for 1D transform</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;stdint.h&gt;<br/>
#include &lt;sleefdft.h&gt;<br/>
<br/>
<b class="type">struct SleefDFT *</b> <b class="func">SleefDFT_double_init1d</b>(<b class="type">uint32_t</b> <i class="var">n</i>, <b class="type">const double *</b><i class="var">in</i>, <b class="type">double *</b><i class="var">out</i>, <b class="type">uint64_t</b> <i class="var">mode</i>);<br/>
<b class="type">struct SleefDFT *</b> <b class="func">SleefDFT_float_init1d</b>(<b class="type">uint32_t</b> <i class="var">n</i>, <b class="type">const float *</b><i class="var">in</i>, <b class="type">float *</b><i class="var">out</i>, <b class="type">uint64_t</b> <i class="var">mode</i>);<br/>
<br/>
Link with -lsleefdft -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions generates and initializes the tables that is used for
  1D transform, and returns the pointer. Size of transform can be
  specified by <i class="var">n</i>. Currently, power-of-two sizes can be only
  specified. The list of the flags that can be passed to <i class="var">mode</i>
  is shown below.
</p>

<div style="margin-top: 1.0cm;"></div>

<table style="text-align:center;" align="center">
  <tr align="center">
    <td class="caption">Table 4.3: Mode flags for SleefDFT_double_init</td>
  </tr>
  <tr align="center">
    <td>
      <table class="lt">
        <tr>
          <td class="lt-hl"></td>
          <td class="lt-hl"></td>
        </tr>
	<tr>
	  <td class="lt-br" align="center">Flag</td>
	  <td class="lt-b" align="center">Meaning</td>
	</tr>
	<tr>
	  <td class="lt-hl"></td>
	  <td class="lt-hl"></td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">SLEEF_MODE_FORWARD</td>
	  <td class="lt-" align="left">Tables are initialized for forward transforms.</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">SLEEF_MODE_BACKWARD</td>
	  <td class="lt-" align="left">Tables are initialized for backward transforms.</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">SLEEF_MODE_COMPLEX</td>
	  <td class="lt-" align="left">Tables are initialized for complex transforms.</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">SLEEF_MODE_REAL</td>
	  <td class="lt-" align="left">Tables are initialized for real transforms.</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">SLEEF_MODE_ALT</td>
	  <td class="lt-" align="left">Tables are initialized for alternative real transforms.</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">SLEEF_MODE_ESTIMATE</td>
	  <td class="lt-" align="left">Execution plans are estimated.</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">SLEEF_MODE_MEASURE</td>
	  <td class="lt-" align="left">Execution plans are measured when they are needed.</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">SLEEF_MODE_VERBOSE</td>
	  <td class="lt-" align="left">Messages are displayed.</td>
	</tr>
	<tr>
	  <td class="lt-br" align="left">SLEEF_MODE_NO_MT</td>
	  <td class="lt-b" align="left">Multithreading will be disabled in the computation for transforms.</td>
	</tr>
      </table>
    </td>
  </tr>
</table>

<p class="header">Return value</p>

<p class="noindent">
  These functions return a pointer to the data that is used for 1D DFT
  computation, or NULL if an error occurred.
</p>

<hr/>

<p class="funcname"><b class="func">SleefDFT_double_init2d</b>, <b class="func">SleefDFT_float_init2d</b> - initialize the tables for 2D transform</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;stdint.h&gt;<br/>
#include &lt;sleefdft.h&gt;<br/>
<br/>
<b class="type">struct SleefDFT *</b> <b class="func">SleefDFT_double_init2d</b>(<b class="type">uint32_t</b> <i class="var">n</i>, <b class="type">uint32_t</b> <i class="var">m</i>, <b class="type">const double *</b><i class="var">in</i>, <b class="type">double *</b><i class="var">out</i>, <b class="type">uint64_t</b> <i class="var">mode</i>);<br/>
<b class="type">struct SleefDFT *</b> <b class="func">SleefDFT_float_init2d</b>(<b class="type">uint32_t</b> <i class="var">n</i>, <b class="type">uint32_t</b> <i class="var">m</i>, <b class="type">const float *</b><i class="var">in</i>, <b class="type">float *</b><i class="var">out</i>, <b class="type">uint64_t</b> <i class="var">mode</i>);<br/>
<br/>
Link with -lsleefdft -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions generates and initilizes the tables that is used for
  2D transform, and returns the pointer. Size of transform can be
  specified by <i class="var">n</i>. Currently, power-of-two sizes can be only
  specified. The list of the flags that can be passed to <i class="var">mode</i>
  is shown below.
</p>

<p class="header">Return value</p>

<p class="noindent">
  These functions return a pointer to the data that is used for 2D DFT
  computation, or NULL if an error occurred.
</p>

<hr/>

<p class="funcname"><b class="func">SleefDFT_double_execute</b>, <b class="func">SleefDFT_float_execute</b> - execute a transform</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;stdint.h&gt;<br/>
#include &lt;sleefdft.h&gt;<br/>
<br/>
<b class="type">void</b> <b class="func">SleefDFT_double_execute</b>(<b class="type">struct SleefDFT *</b><i class="var">ptr</i>, <b class="type">const double *</b><i class="var">in</i>, <b class="type">double *</b><i class="var">out</i>);<br/>
<b class="type">void</b> <b class="func">SleefDFT_float_execute</b>(<b class="type">struct SleefDFT *</b><i class="var">ptr</i>, <b class="type">const float *</b><i class="var">in</i>, <b class="type">float *</b><i class="var">out</i>);<br/>
<br/>
Link with -lsleefdft -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
  <i class="var">ptr</i> is a pointer to the
plan. <i class="var">in</i> and <i class="var">out</i> must be
pointers returned from Sleef_malloc function. You can specify the same
pointer to <i class="var">in</i> and <i class="var">out</i>.
</p>

<hr/>

<p class="funcname"><b class="func">SleefDFT_dispose</b> - dispose the tables for transforms</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;stdint.h&gt;<br/>
#include &lt;sleefdft.h&gt;<br/>
<br/>
<b class="type">void</b> <b class="func">SleefDFT_dispose</b>(<b class="type">struct SleefDFT *</b><i class="var">ptr</i>);<br/>
<br/>
Link with -lsleefdft -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
  This function frees a plan returned
  by <b class="func">SleefDFT_double_init1d</b>, <b class="func">SleefDFT_float_init1d</b>, <b class="func">SleefDFT_double_init2d</b>, or <b class="func">SleefDFT_float_init2d</b> functions.
</p>

