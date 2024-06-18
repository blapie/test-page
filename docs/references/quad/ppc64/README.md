<h1> Quad-precision math library reference (POWER)</h1>

Data types and functions for

  [All architectures](../) |
  [x86](../x86/) |
  [aarch64](../aarch64/) |
  [ppc64](../ppc64/) |
  [s390x](../s390x/) |
  [cuda](../cuda/)

<h2>Table of contents</h2>

<ul class="circle">
  <li><a href="#datatypes">Data types</a></li>
  <li><a href="#access">Functions for accessing elements inside vector variable</a></li>
  <li><a href="#conversion">Conversion functions</a></li>
  <li><a href="#comparison">Comparison and selection functions</a></li>
  <li><a href="#mathfunctions">Math functions</a></li>
</ul>

<h2 id="datatypes">Data types</h2>

<p class="funcname"><b class="type">Sleef_quadx2</b></p>

<p class="header">Description</p>

<p class="noindent">
  <b class="type">Sleef_quadx2</b> is a data type for retaining two QP
  FP numbers. Please
  use <a href="#load"><b class="func">Sleef_loadq2</b></a>, <a href="#store"><b class="func">Sleef_storeq2</b></a>, <a href="#get"><b class="func">Sleef_getq2</b></a>
  and <a href="#set"><b class="func">Sleef_setq2</b></a> functions to access the
  data inside variables in this data type.
</p>


<h2 id="access">Functions for accessing elements inside vector variable</h2>

<p id="load" class="funcname">Load QP FP values into vector variable</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_loadq2</b>( <b class="type">Sleef_quad *</b> <i class="var">ptr</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_loadq2_vsx</b>( <b class="type">Sleef_quad *</b> <i class="var">ptr</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_loadq2_vsx3</b>( <b class="type">Sleef_quad *</b> <i class="var">ptr</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions load QP FP values from memory and store the results
  in a vector variable.
</p>

<hr/>

<p id="store" class="funcname">Store QP FP values in a vector variable to memory</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">void</b> <b class="func">Sleef_storeq2</b>( <b class="type">Sleef_quad *</b> <i class="var">ptr</i>, <b class="type">Sleef_quadx2</b> <i class="var">v</i> );<br/>
<b class="type">void</b> <b class="func">Sleef_storeq2_vsx</b>( <b class="type">Sleef_quad *</b> <i class="var">ptr</i>, <b class="type">Sleef_quadx2</b> <i class="var">v</i> );<br/>
<b class="type">void</b> <b class="func">Sleef_storeq2_vsx3</b>( <b class="type">Sleef_quad *</b> <i class="var">ptr</i>, <b class="type">Sleef_quadx2</b> <i class="var">v</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions store QP FP values in the given variable to memory.
</p>

<hr/>

<p id="get" class="funcname">Extract one element from QP FP vector variable</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quad</b> <b class="func">Sleef_getq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">v</i>, <b class="type">int</b> <i class="var">index</i> );<br/>
<b class="type">Sleef_quad</b> <b class="func">Sleef_getq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">v</i>, <b class="type">int</b> <i class="var">index</i> );<br/>
<b class="type">Sleef_quad</b> <b class="func">Sleef_getq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">v</i>, <b class="type">int</b> <i class="var">index</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions extract the <i class="var">index</i>-th element from
  a QP FP vector variable. 
</p>

<hr/>

<p id="set" class="funcname">Set one element in QP FP vector variable</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_setq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">v</i>, <b class="type">int</b> <i class="var">index</i>, <b class="type">Sleef_quad</b> <i class="var">e</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_setq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">v</i>, <b class="type">int</b> <i class="var">index</i>, <b class="type">Sleef_quad</b> <i class="var">e</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_setq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">v</i>, <b class="type">int</b> <i class="var">index</i>, <b class="type">Sleef_quad</b> <i class="var">e</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions return a QP FP vector in which
  the <i class="var">index</i>-th element is <i class="var">e</i>, and
  other elements are the same as <i class="var">v</i>.
</p>

<hr/>

<p id="splat" class="funcname">Set all elements in QP FP vector to the same value</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_splatq2</b>( <b class="type">Sleef_quad</b> <i class="var">e</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_splatq2_vsx</b>( <b class="type">Sleef_quad</b> <i class="var">e</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_splatq2_vsx3</b>( <b class="type">Sleef_quad</b> <i class="var">e</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions return a QP FP vector in which all elements are set
  to <i class="var">e</i>.
</p>


<h2 id="conversion">Conversion functions</h2>

<p class="funcname">Convert QP number to double-precision number</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">vector double</b> <b class="func">Sleef_cast_to_doubleq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">vector double</b> <b class="func">Sleef_cast_to_doubleq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">vector double</b> <b class="func">Sleef_cast_to_doubleq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions convert a QP FP value to a double-precision value.
</p>

<hr/>

<p class="funcname">Convert double-precision number to QP number</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cast_from_doubleq2</b>( <b class="type">vector double</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cast_from_doubleq2_vsx</b>( <b class="type">vector double</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cast_from_doubleq2_vsx3</b>( <b class="type">vector double</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions convert a double-precision value to a QP FP value.
</p>

<hr/>


<p class="funcname">Convert QP number to 64-bit signed integer</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">vector signed long long</b> <b class="func">Sleef_cast_to_int64q2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">vector signed long long</b> <b class="func">Sleef_cast_to_int64q2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">vector signed long long</b> <b class="func">Sleef_cast_to_int64q2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions convert a QP FP value to a 64-bit signed integer.
</p>

<hr/>


<p class="funcname">Convert 64-bit signed integer to QP number</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cast_from_int64q2</b>( <b class="type">vector signed long long</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cast_from_int64q2_vsx</b>( <b class="type">vector signed long long</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cast_from_int64q2_vsx3</b>( <b class="type">vector signed long long</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions convert a 64-bit signed integer to a QP FP value.
</p>

<hr/>


<p class="funcname">Convert QP number to 64-bit unsigned integer</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">vector unsigned long long</b> <b class="func">Sleef_cast_to_uint64q2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">vector unsigned long long</b> <b class="func">Sleef_cast_to_uint64q2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">vector unsigned long long</b> <b class="func">Sleef_cast_to_uint64q2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions convert a QP FP value to a 64-bit signed integer.
</p>

<hr/>


<p class="funcname">Convert 64-bit unsigned integer to QP number</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cast_from_uint64q2</b>( <b class="type">vector unsigned long long</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cast_from_uint64q2_vsx</b>( <b class="type">vector unsigned long long</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cast_from_uint64q2_vsx3</b>( <b class="type">vector unsigned long long</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These functions convert a 64-bit unsigned integer to a QP FP value.
</p>


<h2 id="comparison">Comparison and selection functions</h2>

<p class="funcname">QP comparison functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpltq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpleq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpgtq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpgeq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpeqq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpneq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpltq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpleq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpgtq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpgeq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpeqq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpneq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpltq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpleq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpgtq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpgeq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpeqq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpneq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions of <a class="underlined"
  href="../#basicComparison">comparison functions</a>.
</p>

<hr/>

<p class="funcname">QP comparison functions of the second kind</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_icmpq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_icmpq1_purec"><b class="func">Sleef_icmpq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Check orderedness</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">vector int</b> <b class="func">Sleef_iunordq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_iunordq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_iunordq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_iunordq1_purec"><b class="func">Sleef_iunordq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Select elements</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_iselectq2</b>( <b class="type">vector int</b> <i class="var">c</i>, <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_iselectq2_vsx</b>( <b class="type">vector int</b> <i class="var">c</i>, <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_iselectq2_vsx3</b>( <b class="type">vector int</b> <i class="var">c</i>, <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions that operate in the same way as the ternary operator.
</p>

<h2 id="mathfunctions">Math functions</h2>

<p class="funcname">QP functions for basic arithmetic operations</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_addq2_u05</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_subq2_u05</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_mulq2_u05</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_divq2_u05</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_negq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_addq2_u05vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_subq2_u05vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_mulq2_u05vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_divq2_u05vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_negq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_addq2_u05vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_subq2_u05vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_mulq2_u05vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_divq2_u05vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i>, <b class="type">Sleef_quadx2</b> <i class="var">b</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_negq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions of <a class="underlined"
  href="../#basicArithmetic">the basic arithmetic operations</a>.
</p>

<hr/>

<p class="funcname">Square root functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_sqrtq2_u05</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_sqrtq2_u05vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_sqrtq2_u05vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_sqrtq1_u05purec"><b class="func">Sleef_sqrtq1_u05purec</b></a>.
</p>

<hr/>

<p class="funcname">Sine functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_sinq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_sinq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_sinq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_sinq1_u10purec"><b class="func">Sleef_sinq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Cosine functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cosq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cosq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_cosq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_cosq1_u10purec"><b class="func">Sleef_cosq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Tangent functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_tanq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_tanq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_tanq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_tanq1_u10purec"><b class="func">Sleef_tanq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Arc sine functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_asinq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_asinq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_asinq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_asinq1_u10purec"><b class="func">Sleef_asinq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Arc cosine functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_acosq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_acosq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_acosq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_acosq1_u10purec"><b class="func">Sleef_acosq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Arc tangent functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_atanq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_atanq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_atanq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_atanq1_u10purec"><b class="func">Sleef_atanq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Base-<i>e</i> exponential functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_expq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_expq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_expq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_expq1_u10purec"><b class="func">Sleef_expq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Base-2 exponential functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_exp2q2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_exp2q2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_exp2q2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_exp2q1_u10purec"><b class="func">Sleef_exp2q1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Base-10 exponentail</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_exp10q2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_exp10q2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_exp10q2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_exp10q1_u10purec"><b class="func">Sleef_exp10q1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Base-<i>e</i> exponential functions minus 1</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_expm1q2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_expm1q2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_expm1q2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_expm1q1_u10purec"><b class="func">Sleef_expm1q1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Natural logarithmic functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_logq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_logq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_logq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_logq1_u10purec"><b class="func">Sleef_logq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Base-2 logarithmic functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_log2q2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_log2q2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_log2q2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_log2q1_u10purec"><b class="func">Sleef_log2q1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Base-10 logarithmic functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_log10q2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_log10q2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_log10q2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_log10q1_u10purec"><b class="func">Sleef_log10q1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Logarithm of one plus argument</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_log1pq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_log1pq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_log1pq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_log1pq1_u10purec"><b class="func">Sleef_log1pq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Power functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_powq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_powq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_powq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_powq1_u10purec"><b class="func">Sleef_powq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Hyperbolic sine functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_sinhq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_sinhq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_sinhq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_sinhq1_u10purec"><b class="func">Sleef_sinhq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Hyperbolic cosine functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_coshq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_coshq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_coshq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_coshq1_u10purec"><b class="func">Sleef_coshq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Hyperbolic tangent functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_tanhq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_tanhq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_tanhq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_tanhq1_u10purec"><b class="func">Sleef_tanhq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Inverse hyperbolic sine functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_asinhq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_asinhq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_asinhq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_asinhq1_u10purec"><b class="func">Sleef_asinhq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Inverse hyperbolic cosine functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_acoshq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_acoshq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_acoshq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_acoshq1_u10purec"><b class="func">Sleef_acoshq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Inverse hyperbolic tangent functions</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_atanhq2_u10</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_atanhq2_u10vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_atanhq2_u10vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_atanhq1_u10purec"><b class="func">Sleef_atanhq1_u10purec</b></a>.
</p>

<hr/>

<p class="funcname">Round to integer towards zero</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_truncq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_truncq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_truncq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_truncq1_purec"><b class="func">Sleef_truncq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Round to integer towards minus infinity</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_floorq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_floorq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_floorq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_floorq1_purec"><b class="func">Sleef_floorq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Round to integer towards plus infinity</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_ceilq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_ceilq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_ceilq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_ceilq1_purec"><b class="func">Sleef_ceilq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Round to integer away from zero</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_roundq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_roundq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_roundq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_roundq1_purec"><b class="func">Sleef_roundq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Round to integer, ties round to even</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_rintq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_rintq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_rintq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_rintq1_purec"><b class="func">Sleef_rintq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Absolute value</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fabsq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fabsq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fabsq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">a</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_fabsq1_purec"><b class="func">Sleef_fabsq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Copy sign of a number</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_copysignq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_copysignq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_copysignq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_copysignq1_purec"><b class="func">Sleef_copysignq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Maximum of two numbers</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fmaxq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fmaxq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fmaxq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_fmaxq1_purec"><b class="func">Sleef_fmaxq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Minimum of two numbers</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fminq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fminq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fminq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_fminq1_purec"><b class="func">Sleef_fminq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Positive difference</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fdimq2_u05</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fdimq2_u05vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fdimq2_u05vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_fdimq1_u05purec"><b class="func">Sleef_fdimq1_u05purec</b></a>.
</p>

<hr/>

<p class="funcname">Floating point remainder</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fmodq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fmodq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fmodq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_fmodq1_purec"><b class="func">Sleef_fmodq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Floating point remainder</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_remainderq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_remainderq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_remainderq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_remainderq1_purec"><b class="func">Sleef_remainderq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Split a number to fractional and integral components</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_frexpq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">vector int *</b> <i class="var">ptr</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_frexpq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">vector int *</b> <i class="var">ptr</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_frexpq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">vector int *</b> <i class="var">ptr</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_frexpq1_purec"><b class="func">Sleef_frexpq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Break a number into integral and fractional parts</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_modfq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2 *</b> <i class="var">ptr</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_modfq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2 *</b> <i class="var">ptr</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_modfq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2 *</b> <i class="var">ptr</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_modfq1_purec"><b class="func">Sleef_modfq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">2D Euclidian distance</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_hypotq2_u05</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_hypotq2_u05vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_hypotq2_u05vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_hypotq1_u05purec"><b class="func">Sleef_hypotq1_u05purec</b></a>.
</p>

<hr/>

<p class="funcname">Fused multiply and accumulate</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fmaq2_u05</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i>, <b class="type">Sleef_quadx2</b> <i class="var">z</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fmaq2_u05vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i>, <b class="type">Sleef_quadx2</b> <i class="var">z</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_fmaq2_u05vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">Sleef_quadx2</b> <i class="var">y</i>, <b class="type">Sleef_quadx2</b> <i class="var">z</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_fmaq1_u05purec"><b class="func">Sleef_fmaq1_u05purec</b></a>.
</p>

<hr/>

<p class="funcname">Multiply by integral power of 2</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_ldexpq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">vector int</b> <i class="var">e</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_ldexpq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">vector int</b> <i class="var">e</i> );<br/>
<b class="type">Sleef_quadx2</b> <b class="func">Sleef_ldexpq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i>, <b class="type">vector int</b> <i class="var">e</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_ldexpq1_purec"><b class="func">Sleef_ldexpq1_purec</b></a>.
</p>

<hr/>

<p class="funcname">Integer exponent of an FP number</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleefquad.h&gt;<br/>
<br/>
<b class="type">vector int</b> <b class="func">Sleef_ilogbq2</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_ilogbq2_vsx</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i> );<br/>
<b class="type">vector int</b> <b class="func">Sleef_ilogbq2_vsx3</b>( <b class="type">Sleef_quadx2</b> <i class="var">x</i> );<br/>
<br/>
<span class="normal">Link with</span> -lsleefquad.
</p>

<p class="header">Description</p>

<p class="noindent">
  These are the vectorized functions
  of <a href="../#Sleef_ilogbq1_purec"><b class="func">Sleef_ilogbq1_purec</b></a>.
</p>

