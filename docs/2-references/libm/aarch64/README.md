---
layout: default
title: AArch64
parent: Single & Double Precision
grand_parent: References
permalink: /2-references/libm/aarch64
---

<h1>Single & Double Precision Math library reference (AArch64)</h1>

<h2>Table of contents</h2>

<ul class="circle">
  <li><a href="#datatypes">Data types</a></li>
  <li><a href="#trig">Trigonometric functions</a></li>
  <li><a href="#pow">Power, exponential, and logarithmic functions</a></li>
  <li><a href="#invtrig">Inverse trigonometric functions</a></li>
  <li><a href="#hyp">Hyperbolic functions and inverse hyperbolic functions</a></li>
  <li><a href="#eg">Error and gamma functions</a></li>
  <li><a href="#nearint">Nearest integer functions</a></li>
  <li><a href="#other">Other functions</a></li>
</ul>

<h2 id="datatypes">Data types for AArch64 architecture</h2>

<p class="funcname"><b class="type">Sleef_float32x4_t_2</b></p>

<p class="header">Description</p>

<p class="noindent">
<b class="type">Sleef_float32x4_t_2</b> is a data type for storing two <b class="type">float32x4_t</b> values,
which is defined in sleef.h as follows:
</p>

<pre class="white">typedef struct {
  float32x4_t x, y;
} Sleef_float32x4_t_2;
</pre>

<hr/>

<p class="funcname"><b class="type">Sleef_float64x2_t_2</b></p>

<p class="header">Description</p>

<p class="noindent">
<b class="type">Sleef_float64x2_t_2</b> is a data type for storing two <b class="type">float64x2_t</b> values,
which is defined in sleef.h as follows:
</p>

<pre class="white">typedef struct {
  float64x2_t x, y;
} Sleef_float64x2_t_2;
</pre>

<hr/>

<p class="funcname"><b class="type">Sleef_svfloat32_t_2</b></p>

<p class="header">Description</p>

<p class="noindent">
<b class="type">Sleef_svfloat32_t_2</b> is a data type for storing two <b class="type">svfloat32_t</b> values,
which is defined in sleef.h as follows:
</p>

<pre class="white">typedef struct {
  svfloat32_t x, y;
} Sleef_svfloat32_t_2;
</pre>

<hr/>

<p class="funcname"><b class="type">Sleef_svfloat64_t_2</b></p>

<p class="header">Description</p>

<p class="noindent">
<b class="type">Sleef_svfloat64_t_2</b> is a data type for storing two <b class="type">svfloat64_t</b> values,
which is defined in sleef.h as follows:
</p>

<pre class="white">typedef struct {
  svfloat64_t x, y;
} Sleef_svfloat64_t_2;
</pre>


<h2 id="trig">Trigonometric Functions</h2>

<p class="funcname">Vectorized double precision sine function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sind2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sind2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_sind2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_sind2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sindx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sindx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_sindx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_sindx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

These are the vectorized functions of [Sleef_sin_u10](../#sin-1ulp) with the same accuracy specification.

<hr/>
<p class="funcname">Vectorized single precision sine function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sinf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sinf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_sinf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_sinf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sinfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sinfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_sinfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_sinfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

These are the vectorized functions of [Sleef_sinf_u10](../#sin-1ulp) with the same accuracy specification.

<hr/>
<p class="funcname">Vectorized double precision sine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sind2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sind2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_sind2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_sind2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sindx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sindx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_sindx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_sindx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sin_u35"><b class="func">Sleef_sin_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision sine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sinf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sinf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_sinf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_sinf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sinfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sinfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_sinfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_sinfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sinf_u35"><b class="func">Sleef_sinf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision cosine function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cosd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cosd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_cosd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_cosd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cosdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cosdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_cosdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_cosdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cos_u10"><b class="func">Sleef_cos_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision cosine function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cosf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cosf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_cosf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_cosf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cosfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cosfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_cosfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_cosfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cosf_u10"><b class="func">Sleef_cosf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision cosine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cosd2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cosd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_cosd2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_cosd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cosdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cosdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_cosdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_cosdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cos_u35"><b class="func">Sleef_cos_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision cosine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cosf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cosf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_cosf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_cosf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cosfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cosfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_cosfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_cosfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cosf_u35"><b class="func">Sleef_cosf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision combined sine and cosine function with 0.506 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_sincosd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_sincosd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_cinz_sincosd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_finz_sincosd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_sincosdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_sincosdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_cinz_sincosdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_finz_sincosdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sincos_u10"><b class="func">Sleef_sincos_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision combined sine and cosine function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_sincosf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_sincosf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_cinz_sincosf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_finz_sincosf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_sincosfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_sincosfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_cinz_sincosfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_finz_sincosfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sincosf_u10"><b class="func">Sleef_sincosf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision combined sine and cosine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_sincosd2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_sincosd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_cinz_sincosd2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_finz_sincosd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_sincosdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_sincosdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_cinz_sincosdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_finz_sincosdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sincos_u35"><b class="func">Sleef_sincos_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision combined sine and cosine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_sincosf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_sincosf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_cinz_sincosf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_finz_sincosf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_sincosfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_sincosfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_cinz_sincosfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_finz_sincosfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sincosf_u35"><b class="func">Sleef_sincosf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision sine function with 0.506 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sinpid2_u05</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sinpid2_u05advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_sinpid2_u05advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_sinpid2_u05advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sinpidx_u05sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sinpidx_u05svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_sinpidx_u05svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_sinpidx_u05sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sinpi_u05"><b class="func">Sleef_sinpi_u05</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision sine function with 0.506 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sinpif4_u05</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sinpif4_u05advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_sinpif4_u05advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_sinpif4_u05advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sinpifx_u05sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sinpifx_u05svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_sinpifx_u05svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_sinpifx_u05sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sinpif_u05"><b class="func">Sleef_sinpif_u05</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision cosine function with 0.506 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cospid2_u05</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cospid2_u05advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_cospid2_u05advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_cospid2_u05advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cospidx_u05sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cospidx_u05svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_cospidx_u05svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_cospidx_u05sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cospi_u05"><b class="func">Sleef_cospi_u05</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision cosine function with 0.506 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cospif4_u05</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cospif4_u05advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_cospif4_u05advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_cospif4_u05advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cospifx_u05sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cospifx_u05svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_cospifx_u05svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_cospifx_u05sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cospif_u05"><b class="func">Sleef_cospif_u05</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision combined sine and cosine function with 0.506 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_sincospid2_u05</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_sincospid2_u05advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_cinz_sincospid2_u05advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_finz_sincospid2_u05advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_sincospidx_u05sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_sincospidx_u05svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_cinz_sincospidx_u05svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_finz_sincospidx_u05sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sincospi_u05"><b class="func">Sleef_sincospi_u05</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision combined sine and cosine function with 0.506 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_sincospif4_u05</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_sincospif4_u05advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_cinz_sincospif4_u05advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_finz_sincospif4_u05advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_sincospifx_u05sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_sincospifx_u05svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_cinz_sincospifx_u05svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_finz_sincospifx_u05sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sincospif_u05"><b class="func">Sleef_sincospif_u05</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision combined sine and cosine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_sincospid2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_sincospid2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_cinz_sincospid2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_finz_sincospid2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_sincospidx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_sincospidx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_cinz_sincospidx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_finz_sincospidx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sincospi_u35"><b class="func">Sleef_sincospi_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision combined sine and cosine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_sincospif4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_sincospif4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_cinz_sincospif4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_finz_sincospif4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_sincospifx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_sincospifx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_cinz_sincospifx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_finz_sincospifx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sincospif_u35"><b class="func">Sleef_sincospif_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision tangent function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_tand2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_tand2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_tand2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_tand2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_tandx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_tandx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_tandx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_tandx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_tan_u10"><b class="func">Sleef_tan_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision tangent function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_tanf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_tanf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_tanf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_tanf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_tanfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_tanfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_tanfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_tanfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_tanf_u10"><b class="func">Sleef_tanf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision tangent function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_tand2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_tand2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_tand2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_tand2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_tandx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_tandx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_tandx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_tandx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_tan_u35"><b class="func">Sleef_tan_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision tangent function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_tanf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_tanf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_tanf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_tanf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_tanfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_tanfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_tanfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_tanfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_tanf_u35"><b class="func">Sleef_tanf_u35</b></a> with the same accuracy specification.
</p>

<h2 id="pow">Power, exponential, and logarithmic function</h2>

<p class="funcname">Vectorized double precision power function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_powd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_powd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_powd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_powd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_powdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_powdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_powdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_powdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_pow_u10"><b class="func">Sleef_pow_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision power function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_powf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_powf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_powf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_powf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_powfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_powfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_powfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_powfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_powf_u10"><b class="func">Sleef_powf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision natural logarithmic function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_logd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_logd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_logd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_logd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_logdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_logdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_logdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_logdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_log_u10"><b class="func">Sleef_log_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision natural logarithmic function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_logf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_logf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_logf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_logf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_logfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_logfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_logfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_logfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_logf_u10"><b class="func">Sleef_logf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision natural logarithmic function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_logd2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_logd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_logd2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_logd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_logdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_logdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_logdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_logdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_log_u35"><b class="func">Sleef_log_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision natural logarithmic function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_logf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_logf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_logf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_logf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_logfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_logfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_logfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_logfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_logf_u35"><b class="func">Sleef_logf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision base-10 logarithmic function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_log10d2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_log10d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_log10d2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_log10d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_log10dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_log10dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_log10dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_log10dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_log10_u10"><b class="func">Sleef_log10_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision base-10 logarithmic function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_log10f4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_log10f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_log10f4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_log10f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_log10fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_log10fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_log10fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_log10fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_log10f_u10"><b class="func">Sleef_log10f_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision base-2 logarithmic function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_log2d2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_log2d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_log2d2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_log2d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_log2dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_log2dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_log2dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_log2dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_log2_u10"><b class="func">Sleef_log2_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision base-2 logarithmic function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_log2f4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_log2f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_log2f4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_log2f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_log2fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_log2fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_log2fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_log2fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_log2f_u10"><b class="func">Sleef_log2f_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision logarithm of one plus argument with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_log1pd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_log1pd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_log1pd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_log1pd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_log1pdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_log1pdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_log1pdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_log1pdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_log1p_u10"><b class="func">Sleef_log1p_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision logarithm of one plus argument with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_log1pf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_log1pf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_log1pf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_log1pf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_log1pfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_log1pfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_log1pfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_log1pfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_log1pf_u10"><b class="func">Sleef_log1pf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision base-<i>e</i> exponential function function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_expd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_expd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_expd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_expd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_expdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_expdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_expdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_expdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_exp_u10"><b class="func">Sleef_exp_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision base-<i>e</i> exponential function function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_expf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_expf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_expf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_expf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_expfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_expfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_expfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_expfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_expf_u10"><b class="func">Sleef_expf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision base-<i>2</i> exponential function function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_exp2d2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_exp2d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_exp2d2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_exp2d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_exp2dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_exp2dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_exp2dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_exp2dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_exp2_u10"><b class="func">Sleef_exp2_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision base-<i>2</i> exponential function function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_exp2f4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_exp2f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_exp2f4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_exp2f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_exp2fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_exp2fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_exp2fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_exp2fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_exp2f_u10"><b class="func">Sleef_exp2f_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision base-10 exponential function function with 1.09 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_exp10d2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_exp10d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_exp10d2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_exp10d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_exp10dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_exp10dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_exp10dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_exp10dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_exp10_u10"><b class="func">Sleef_exp10_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision base-10 exponential function function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_exp10f4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_exp10f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_exp10f4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_exp10f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_exp10fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_exp10fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_exp10fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_exp10fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_exp10f_u10"><b class="func">Sleef_exp10f_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision base-<i>e</i> exponential function minus 1 with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_expm1d2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_expm1d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_expm1d2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_expm1d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_expm1dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_expm1dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_expm1dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_expm1dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_expm1_u10"><b class="func">Sleef_expm1_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision base-<i>e</i> exponential function minus 1 with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_expm1f4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_expm1f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_expm1f4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_expm1f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_expm1fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_expm1fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_expm1fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_expm1fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_expm1f_u10"><b class="func">Sleef_expm1f_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision square root function with 0.5001 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sqrtd2_u05</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sqrtd2_u05advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_sqrtd2_u05advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_sqrtd2_u05advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sqrtdx_u05sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sqrtdx_u05svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_sqrtdx_u05svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_sqrtdx_u05sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sqrt_u05"><b class="func">Sleef_sqrt_u05</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision square root function with 0.5001 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sqrtf4_u05</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sqrtf4_u05advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_sqrtf4_u05advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_sqrtf4_u05advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sqrtfx_u05sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sqrtfx_u05svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_sqrtfx_u05svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_sqrtfx_u05sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sqrtf_u05"><b class="func">Sleef_sqrtf_u05</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision square root function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sqrtd2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sqrtd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_sqrtd2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_sqrtd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sqrtdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sqrtdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_sqrtdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_sqrtdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sqrt_u35"><b class="func">Sleef_sqrt_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision square root function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sqrtf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sqrtf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_sqrtf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_sqrtf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sqrtfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sqrtfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_sqrtfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_sqrtfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sqrtf_u35"><b class="func">Sleef_sqrtf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision cubic root function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cbrtd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cbrtd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_cbrtd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_cbrtd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cbrtdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cbrtdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_cbrtdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_cbrtdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cbrt_u10"><b class="func">Sleef_cbrt_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision cubic root function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cbrtf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cbrtf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_cbrtf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_cbrtf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cbrtfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cbrtfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_cbrtfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_cbrtfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cbrtf_u10"><b class="func">Sleef_cbrtf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision cubic root function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cbrtd2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cbrtd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_cbrtd2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_cbrtd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cbrtdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cbrtdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_cbrtdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_cbrtdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cbrt_u35"><b class="func">Sleef_cbrt_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision cubic root function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cbrtf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cbrtf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_cbrtf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_cbrtf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cbrtfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cbrtfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_cbrtfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_cbrtfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cbrtf_u35"><b class="func">Sleef_cbrtf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision 2D Euclidian distance function with 0.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_hypotd2_u05</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_hypotd2_u05advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_hypotd2_u05advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_hypotd2_u05advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_hypotdx_u05sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_hypotdx_u05svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_hypotdx_u05svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_hypotdx_u05sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_hypot_u05"><b class="func">Sleef_hypot_u05</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision 2D Euclidian distance function with 0.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_hypotf4_u05</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_hypotf4_u05advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_hypotf4_u05advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_hypotf4_u05advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_hypotfx_u05sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_hypotfx_u05svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_hypotfx_u05svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_hypotfx_u05sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_hypotf_u05"><b class="func">Sleef_hypotf_u05</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision 2D Euclidian distance function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_hypotd2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_hypotd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_hypotd2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_hypotd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_hypotdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_hypotdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_hypotdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_hypotdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_hypot_u35"><b class="func">Sleef_hypot_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision 2D Euclidian distance function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_hypotf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_hypotf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_hypotf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_hypotf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_hypotfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_hypotfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_hypotfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_hypotfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_hypotf_u35"><b class="func">Sleef_hypotf_u35</b></a> with the same accuracy specification.
</p>


<h2 id="invtrig">Inverse Trigonometric Functions</h2>

<p class="funcname">Vectorized double precision arc sine function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_asind2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_asind2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_asind2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_asind2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_asindx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_asindx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_asindx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_asindx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_asin_u10"><b class="func">Sleef_asin_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision arc sine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_asinf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_asinf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_asinf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_asinf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_asinfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_asinfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_asinfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_asinfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_asinf_u10"><b class="func">Sleef_asinf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision arc sine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_asind2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_asind2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_asind2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_asind2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_asindx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_asindx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_asindx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_asindx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_asin_u35"><b class="func">Sleef_asin_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision arc sine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_asinf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_asinf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_asinf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_asinf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_asinfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_asinfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_asinfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_asinfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_asinf_u35"><b class="func">Sleef_asinf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision arc cosine function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_acosd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_acosd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_acosd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_acosd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_acosdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_acosdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_acosdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_acosdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_acos_u10"><b class="func">Sleef_acos_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision arc cosine function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_acosf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_acosf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_acosf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_acosf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_acosfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_acosfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_acosfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_acosfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_acosf_u10"><b class="func">Sleef_acosf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision arc cosine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_acosd2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_acosd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_acosd2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_acosd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_acosdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_acosdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_acosdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_acosdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_acos_u35"><b class="func">Sleef_acos_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision arc cosine function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_acosf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_acosf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_acosf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_acosf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_acosfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_acosfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_acosfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_acosfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_acosf_u35"><b class="func">Sleef_acosf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision arc tangent function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_atand2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_atand2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_atand2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_atand2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_atandx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_atandx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_atandx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_atandx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_atan_u10"><b class="func">Sleef_atan_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision arc tangent function with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_atanf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_atanf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_atanf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_atanf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_atanfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_atanfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_atanfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_atanfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_atanf_u10"><b class="func">Sleef_atanf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision arc tangent function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_atand2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_atand2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_atand2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_atand2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_atandx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_atandx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_atandx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_atandx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_atan_u35"><b class="func">Sleef_atan_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision arc tangent function with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_atanf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_atanf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_atanf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_atanf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_atanfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_atanfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_atanfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_atanfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_atanf_u35"><b class="func">Sleef_atanf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision arc tangent function of two variables with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_atan2d2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_atan2d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_atan2d2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_atan2d2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_atan2dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_atan2dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_atan2dx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_atan2dx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_atan2_u10"><b class="func">Sleef_atan2_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision arc tangent function of two variables with 1.0 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_atan2f4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_atan2f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_atan2f4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_atan2f4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_atan2fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_atan2fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_atan2fx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_atan2fx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_atan2f_u10"><b class="func">Sleef_atan2f_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision arc tangent function of two variables with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_atan2d2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_atan2d2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_atan2d2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_atan2d2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_atan2dx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_atan2dx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_atan2dx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_atan2dx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_atan2_u35"><b class="func">Sleef_atan2_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision arc tangent function of two variables with 3.5 ULP error bound</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_atan2f4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_atan2f4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_atan2f4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_atan2f4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_atan2fx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_atan2fx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_atan2fx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_atan2fx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_atan2f_u35"><b class="func">Sleef_atan2f_u35</b></a> with the same accuracy specification.
</p>



<h2 id="hyp">Hyperbolic function and inverse hyperbolic function</h2>

<p class="funcname">Vectorized double precision hyperbolic sine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sinhd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sinhd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_sinhd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_sinhd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sinhdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sinhdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_sinhdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_sinhdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sinh_u10"><b class="func">Sleef_sinh_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision hyperbolic sine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sinhf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sinhf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_sinhf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_sinhf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sinhfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sinhfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_sinhfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_sinhfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sinhf_u10"><b class="func">Sleef_sinhf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision hyperbolic sine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sinhd2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_sinhd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_sinhd2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_sinhd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sinhdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_sinhdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_sinhdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_sinhdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sinh_u35"><b class="func">Sleef_sinh_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision hyperbolic sine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sinhf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_sinhf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_sinhf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_sinhf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sinhfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_sinhfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_sinhfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_sinhfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_sinhf_u35"><b class="func">Sleef_sinhf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision hyperbolic cosine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_coshd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_coshd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_coshd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_coshd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_coshdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_coshdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_coshdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_coshdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cosh_u10"><b class="func">Sleef_cosh_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision hyperbolic cosine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_coshf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_coshf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_coshf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_coshf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_coshfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_coshfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_coshfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_coshfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_coshf_u10"><b class="func">Sleef_coshf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision hyperbolic cosine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_coshd2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_coshd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_coshd2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_coshd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_coshdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_coshdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_coshdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_coshdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_cosh_u35"><b class="func">Sleef_cosh_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision hyperbolic cosine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_coshf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_coshf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_coshf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_coshf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_coshfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_coshfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_coshfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_coshfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_coshf_u35"><b class="func">Sleef_coshf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision hyperbolic tangent function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_tanhd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_tanhd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_tanhd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_tanhd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_tanhdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_tanhdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_tanhdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_tanhdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_tanh_u10"><b class="func">Sleef_tanh_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision hyperbolic tangent function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_tanhf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_tanhf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_tanhf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_tanhf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_tanhfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_tanhfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_tanhfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_tanhfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_tanhf_u10"><b class="func">Sleef_tanhf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision hyperbolic tangent function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_tanhd2_u35</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_tanhd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_tanhd2_u35advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_tanhd2_u35advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_tanhdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_tanhdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_tanhdx_u35svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_tanhdx_u35sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_tanh_u35"><b class="func">Sleef_tanh_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision hyperbolic tangent function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_tanhf4_u35</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_tanhf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_tanhf4_u35advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_tanhf4_u35advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_tanhfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_tanhfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_tanhfx_u35svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_tanhfx_u35sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_tanhf_u35"><b class="func">Sleef_tanhf_u35</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision inverse hyperbolic sine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_asinhd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_asinhd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_asinhd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_asinhd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_asinhdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_asinhdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_asinhdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_asinhdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_asinh_u10"><b class="func">Sleef_asinh_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision inverse hyperbolic sine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_asinhf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_asinhf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_asinhf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_asinhf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_asinhfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_asinhfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_asinhfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_asinhfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_asinhf_u10"><b class="func">Sleef_asinhf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision inverse hyperbolic cosine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_acoshd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_acoshd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_acoshd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_acoshd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_acoshdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_acoshdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_acoshdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_acoshdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_acosh_u10"><b class="func">Sleef_acosh_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision inverse hyperbolic cosine function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_acoshf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_acoshf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_acoshf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_acoshf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_acoshfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_acoshfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_acoshfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_acoshfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_acoshf_u10"><b class="func">Sleef_acoshf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision inverse hyperbolic tangent function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_atanhd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_atanhd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_atanhd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_atanhd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_atanhdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_atanhdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_atanhdx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_atanhdx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_atanh_u10"><b class="func">Sleef_atanh_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision inverse hyperbolic tangent function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_atanhf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_atanhf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_atanhf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_atanhf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_atanhfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_atanhfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_atanhfx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_atanhfx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_atanhf_u10"><b class="func">Sleef_atanhf_u10</b></a> with the same accuracy specification.
</p>


<h2 id="eg">Error and gamma function</h2>

<p class="funcname">Vectorized double precision error function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_erfd2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_erfd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_erfd2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_erfd2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_erfdx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_erfdx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_erfdx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_erfdx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_erf_u10"><b class="func">Sleef_erf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision error function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_erff4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_erff4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_erff4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_erff4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_erffx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_erffx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_erffx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_erffx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_erff_u10"><b class="func">Sleef_erff_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision complementary error function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_erfcd2_u15</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_erfcd2_u15advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_erfcd2_u15advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_erfcd2_u15advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_erfcdx_u15sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_erfcdx_u15svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_erfcdx_u15svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_erfcdx_u15sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_erfc_u15"><b class="func">Sleef_erfc_u15</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision complementary error function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_erfcf4_u15</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_erfcf4_u15advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_erfcf4_u15advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_erfcf4_u15advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_erfcfx_u15sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_erfcfx_u15svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_erfcfx_u15svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_erfcfx_u15sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_erfcf_u15"><b class="func">Sleef_erfcf_u15</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision gamma function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_tgammad2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_tgammad2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_tgammad2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_tgammad2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_tgammadx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_tgammadx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_tgammadx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_tgammadx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_tgamma_u10"><b class="func">Sleef_tgamma_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision gamma function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_tgammaf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_tgammaf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_cinz_tgammaf4_u10advsimdnofma</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_tgammaf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_tgammafx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_tgammafx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_tgammafx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_tgammafx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_tgammaf_u10"><b class="func">Sleef_tgammaf_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision log gamma function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_lgammad2_u10</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_lgammad2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_cinz_lgammad2_u10advsimdnofma</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_finz_lgammad2_u10advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_lgammadx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_lgammadx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_cinz_lgammadx_u10svenofma</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_finz_lgammadx_u10sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_lgamma_u10"><b class="func">Sleef_lgamma_u10</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision log gamma function</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_lgammaf4_u10</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_lgammaf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_finz_lgammaf4_u10advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_lgammafx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_lgammafx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_cinz_lgammafx_u10svenofma</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_finz_lgammafx_u10sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_lgammaf_u10"><b class="func">Sleef_lgammaf_u10</b></a> with the same accuracy specification.
</p>


<h2 id="nearint">Nearest integer function</h2>

<p class="funcname">Vectorized double precision function for rounding to integer towards zero</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_truncd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_truncd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_truncdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_trunc"><b class="func">Sleef_trunc</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for rounding to integer towards zero</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_truncf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_truncf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_truncfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_truncf"><b class="func">Sleef_truncf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for rounding to integer towards negative infinity</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_floord2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_floord2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_floordx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_floor"><b class="func">Sleef_floor</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for rounding to integer towards negative infinity</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_floorf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_floorf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_floorfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_floorf"><b class="func">Sleef_floorf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for rounding to integer towards positive infinity</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_ceild2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_ceild2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_ceildx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_ceil"><b class="func">Sleef_ceil</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for rounding to integer towards positive infinity</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_ceilf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_ceilf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_ceilfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_ceilf"><b class="func">Sleef_ceilf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for rounding to nearest integer</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_roundd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_roundd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_rounddx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_round"><b class="func">Sleef_round</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for rounding to nearest integer</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_roundf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_roundf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_roundfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_roundf"><b class="func">Sleef_roundf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for rounding to nearest integer</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_rintd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_rintd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_rintdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_rint"><b class="func">Sleef_rint</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for rounding to nearest integer</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_rintf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_rintf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_rintfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_rintf"><b class="func">Sleef_rintf</b></a> with the same accuracy specification.
</p>


<h2 id="other">Other function</h2>

<p class="funcname">Vectorized double precision function for fused multiply-accumulation</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fmad2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>, <b class="type">float64x2_t</b> <i class="var">c</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fmad2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>, <b class="type">float64x2_t</b> <i class="var">c</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_fmadx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>, <b class="type">svfloat64_t</b> <i class="var">c</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fma"><b class="func">Sleef_fma</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for fused multiply-accumulation</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fmaf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>, <b class="type">float32x4_t</b> <i class="var">c</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fmaf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>, <b class="type">svfloat32_t</b> <i class="var">c</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_fmafx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>, <b class="type">svfloat32_t</b> <i class="var">c</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fmaf"><b class="func">Sleef_fmaf</b></a> with the same accuracy specification.
</p>

<hr/>

<p class="funcname">Vectorized double precision FP remainder</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fmodd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fmodd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_fmoddx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fmod"><b class="func">Sleef_fmod</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision FP remainder</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fmodf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fmodf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_fmodfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fmodf"><b class="func">Sleef_fmodf</b></a> with the same accuracy specification.
</p>

<hr/>

<p class="funcname">Vectorized double precision FP remainder</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_remainderd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_remainderd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_remainderdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_remainder"><b class="func">Sleef_remainder</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision FP remainder</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_remainderf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_remainderf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_remainderfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_remainderf"><b class="func">Sleef_remainderf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for multiplying by integral power of 2</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_ldexpd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">int32x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_ldexpd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">int32x2_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_ldexpdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svint32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_ldexp"><b class="func">Sleef_ldexp</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for obtaining fractional component of an FP number</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_frfrexpd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_frfrexpd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_frfrexpdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_frfrexp"><b class="func">Sleef_frfrexp</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for obtaining fractional component of an FP number</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_frfrexpf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_frfrexpf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_frfrexpfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_frfrexpf"><b class="func">Sleef_frfrexpf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for obtaining integral component of an FP number</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">int32x2_t</b> <b class="func">Sleef_expfrexpd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">int32x2_t</b> <b class="func">Sleef_expfrexpd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">svint32_t</b> <b class="func">Sleef_expfrexpdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_expfrexp"><b class="func">Sleef_expfrexp</b></a> with the same accuracy specification.
</p>

<hr/>

<p class="funcname">Vectorized double precision function for getting integer exponent</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">int32x2_t</b> <b class="func">Sleef_ilogbd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">int32x2_t</b> <b class="func">Sleef_ilogbd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">svint32_t</b> <b class="func">Sleef_ilogbdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_ilogb"><b class="func">Sleef_ilogb</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision signed integral and fractional values</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_modfd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float64x2_t_2</b> <b class="func">Sleef_modfd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat64_t_2</b> <b class="func">Sleef_modfdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_modf"><b class="func">Sleef_modf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision signed integral and fractional values</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_modff4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_float32x4_t_2</b> <b class="func">Sleef_modff4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">Sleef_svfloat32_t_2</b> <b class="func">Sleef_modffx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_modff"><b class="func">Sleef_modff</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for calculating the absolute value</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fabsd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fabsd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_fabsdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fabs"><b class="func">Sleef_fabs</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for calculating the absolute value</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fabsf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fabsf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_fabsfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fabsf"><b class="func">Sleef_fabsf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for copying signs</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_copysignd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_copysignd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_copysigndx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_copysign"><b class="func">Sleef_copysign</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for copying signs</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_copysignf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_copysignf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_copysignfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_copysignf"><b class="func">Sleef_copysignf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for determining maximum of two values</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fmaxd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fmaxd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_fmaxdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fmax"><b class="func">Sleef_fmax</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for determining maximum of two values</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fmaxf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fmaxf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_fmaxfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fmaxf"><b class="func">Sleef_fmaxf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for determining minimum of two values</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fmind2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fmind2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_fmindx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fmin"><b class="func">Sleef_fmin</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for determining minimum of two values</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fminf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fminf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_fminfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fminf"><b class="func">Sleef_fminf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function to calculate positive difference of two values</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fdimd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_fdimd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_fdimdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fdim"><b class="func">Sleef_fdim</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function to calculate positive difference of two values</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fdimf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_fdimf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_fdimfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_fdimf"><b class="func">Sleef_fdimf</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized double precision function for obtaining the next representable FP value</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_nextafterd2</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">float64x2_t</b> <b class="func">Sleef_nextafterd2_advsimd</b>(<b class="type">float64x2_t</b> <i class="var">a</i>, <b class="type">float64x2_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat64_t</b> <b class="func">Sleef_nextafterdx_sve</b>(<b class="type">svfloat64_t</b> <i class="var">a</i>, <b class="type">svfloat64_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_nextafter"><b class="func">Sleef_nextafter</b></a> with the same accuracy specification.
</p>

<hr/>
<p class="funcname">Vectorized single precision function for obtaining the next representable FP value</p>

<p class="header">Synopsis</p>

<p class="synopsis">
#include &lt;sleef.h&gt;<br/>
<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_nextafterf4</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">float32x4_t</b> <b class="func">Sleef_nextafterf4_advsimd</b>(<b class="type">float32x4_t</b> <i class="var">a</i>, <b class="type">float32x4_t</b> <i class="var">b</i>);<br/>
<b class="type">svfloat32_t</b> <b class="func">Sleef_nextafterfx_sve</b>(<b class="type">svfloat32_t</b> <i class="var">a</i>, <b class="type">svfloat32_t</b> <i class="var">b</i>);<br/>
<br/>
<span class="normal">Link with</span> -lsleef.
</p>

<p class="header">Description</p>

<p class="noindent">
These are the vectorized functions of <a href="../#Sleef_nextafterf"><b class="func">Sleef_nextafterf</b></a> with the same accuracy specification.
</p>
