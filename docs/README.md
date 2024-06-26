---
layout: home
title: Home
nav_order: 1
permalink: /
---

<h1>Home</h1>

<h2>Table of contents</h2>

  [Overview](#overview) |
  [Supported environment](#environment) |
  [Credit](#credit) |
  [Partners](#partners) |
  [License](#license) |
  [History](#history) |
  [Related](#related) |
  [Publication](#publication)

<h2 id="overview">Overview</h2>

<p class="noindent">
  SLEEF stands for SIMD Library for Evaluating Elementary
  Functions. It implements manually <a class="underlined"
  href="https://en.wikipedia.org/wiki/Automatic_vectorization">vectorized</a>
  versions of all C99 real floating point math functions. It can
  utilize SIMD instructions that are available on modern
  processors. SLEEF is designed to effciently perform computation with
  SIMD instructions by reducing the use of conditional branches and
  scatter/gather memory access. Our <a class="underlined"
  href="5-performance">benchmarks</a> show that the performance of
  SLEEF is comparable to that of the best commercial library.
</p>

<p>
  Unlike closed-source commercial libraries, SLEEF is designed to work
  with various architectures, operating systems and compilers. It is
  distributed under <a class="underlined"
  href="http://www.boost.org/users/license.html">the Boost Software
  License</a>, which is a permissive open source license. SLEEF can be
  easily ported to other architectures by writing a helper file, which
  is a thin abstraction layer of SIMD intrinsics. SLEEF also
  provides <a class="underlined"
  href="3-extra#dispatcher">dispatchers</a> that
  automatically choose the best subroutines for the computer on which
  the library is executed. In order to further optimize the
  application code that calls SLEEF functions,
  <a class="underlined" href="3-extra#lto">link time
  optimization(LTO)</a> can be used to reduce the overhead of
  functions calls, and the build system of SLEEF supports usage of
  LTO. The library also has a functionality to generate
  <a class="underlined" href="3-extra#inline">header
  files</a> in which the library functions are all defined as inline
  functions. SLEEF can be used for <a class="underlined"
  href="2-references/libm/cuda">GPGPU</a> and <a class="underlined"
  href="3-extra#wasm">WebAssembly</a> with these header
  files. In addition to the vectorized functions, SLEEF provides
  scalar functions. Calls to these scalar SLEEF functions can be
  <a class="underlined"
  href="3-extra#vectorizing">auto-vectorized</a> by GCC.
</p>

<p>
  The library contains implementations of all C99 real FP math
  functions in double precision and single precision. Different
  accuracy of the results can be chosen for a subset of the elementary
  functions; for this subset there are versions with up to
  1 <a class="underlined" href="3-extra#ulp">ULP</a> error
  (which is the maximum error, not the average) and even faster
  versions with a few ULPs of error. For non-finite inputs and
  outputs, the functions return correct results as specified in the
  C99 standard. All the functions in the library
  are <a class="underlined" href="4-tools#testerlibm">thoroughly
  tested</a> and confirmed that the evaluation error is within the
  designed limit by comparing the returned values against
  high-precision evaluation using the GNU MPFR Library.
</p>

<p>
  As of version 3.6, SLEEF also includes a <a class="underlined"
  href="2-references/quad">quad-precision math library</a>. This library
  includes fully vectorized IEEE 754 quadruple-precision (QP)
  functions that correspond to the standard C math functions. It also
  includes I/O functions for converting between QP numbers and
  strings.
</p>

<p>
  SLEEF also includes a library of <a class="underlined"
  href="2-references/dft">discrete Fourier transform(DFT)</a>. These
  subroutines are fully vectorized, heavily unrolled, and parallelized
  in such a way that modern SIMD instructions and multiple cores can
  be utilized for efficient computation. It has an API similar to that
  of FFTW for easy migration. The subroutines can utilize long vectors
  up to 2048 bits. The helper files for abstracting SIMD intrinsics
  are shared with SLEEF libm, and thus it is easy to port the DFT
  subroutines to other architectures. <a class="underlined"
  href="https://github.com/shibatch/sleef/wiki/DFT-Performance">Preliminary
  results of benchmark</a> are now available.
</p>

<h2 id="environment">Supported environments</h2>

<p class="noindent">
  This library supports the following architectures :
</p>

<div><br/></div>

<ul class="disc">
  <li><a class="underlined" href="2-references/libm/x86">x86</a> - SSE2, SSE4.1,
  AVX, AVX2+FMA3, AVX512F</li>
  <li><a class="underlined" href="2-references/libm/aarch64">AArch64</a> - Advanced SIMD, SVE</li>
  <li><a class="underlined" href="2-references/libm/aarch32">AArch32</a> - NEON</li>
  <li><a class="underlined" href="2-references/libm/ppc64">PowerPC64</a> - VSX (POWER8), VSX-3 (POWER9)</li>
  <li><a class="underlined" href="2-references/libm/s390x">System/390</a> - VXE (z14), VXE2 (z15)</li>
  <li>RISC-V - RVV1, RVV2</li>
  <li><a class="underlined" href="2-references/libm/cuda">CUDA</a></li>
  <li><a class="underlined" href="3-extra#wasm">WebAssembly</a> - SSE2</li>
</ul>

<div><br/></div>

<p>
  The supported combinations of the architecture, operating system and
  compiler are shown in Table 1.1.
</p>

<div style="margin-top: 1.0cm;"></div>

<table style="text-align:center;" align="center">
  <tr align="center">
    <td class="caption">Table 1.1: Environment support matrix</td>
  </tr>
  <tr align="center">
    <td>
      <table class="lt">
        <tr>
          <td class="lt-hl"></td>
          <td class="lt-hl"></td>
          <td class="lt-hl"></td>
          <td class="lt-hl"></td>
          <td class="lt-hl"></td>
        </tr>
	<tr>
	  <td class="lt-br"></td>
	  <td class="lt-blr" align="center">GCC</td>
	  <td class="lt-br" align="center">Clang</td>
	  <td class="lt-br" align="center">Intel Compiler</td>
	  <td class="lt-b" align="center">MSVC</td>
	</tr>
        <tr>
          <td class="lt-hl"></td>
	  <td class="lt-hl"></td>
          <td class="lt-hl"></td>
          <td class="lt-hl"></td>
          <td class="lt-hl"></td>
        </tr>
	<tr>
	  <td class="lt-r" align="left">x86_64, Linux</td>
	  <td class="lt-lr" align="center">Supported</td>
	  <td class="lt-r" align="center">Supported</td>
	  <td class="lt-r" align="center">Supported</td>
	  <td class="lt-" align="center">N/A</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">AArch64, Linux</td>
	  <td class="lt-lr" align="center">Supported</td>
	  <td class="lt-r" align="center">Supported</td>
	  <td class="lt-r" align="center">N/A</td>
	  <td class="lt-" align="center">N/A</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">x86_64, macOS</td>
	  <td class="lt-lr" align="center">Supported(*2)</td>
	  <td class="lt-r" align="center">Supported(*2)</td>
	  <td class="lt-r" align="center"></td>
	  <td class="lt-" align="center">N/A</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">x86_64, Windows</td>
	  <td class="lt-lr" align="center">Supported(Cygwin)(*3)</td>
	  <td class="lt-r" align="center"><a class="underlined" href="1-user-guide#cow">Supported</a></td>
	  <td class="lt-r" align="center"></td>
	  <td class="lt-" align="center"><a class="underlined" href="1-user-guide#MSVC">Supported</a></td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">AArch32, Linux</td>
	  <td class="lt-lr" align="center">Supported(*1)</td>
	  <td class="lt-r" align="center">Supported(*1)</td>
	  <td class="lt-r" align="center">N/A</td>
	  <td class="lt-" align="center">N/A</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">PowerPC (64 bit), Linux</td>
	  <td class="lt-lr" align="center">Supported</td>
	  <td class="lt-r" align="center">Supported</td>
	  <td class="lt-r" align="center">N/A</td>
	  <td class="lt-" align="center">N/A</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">System/390 (64 bit), Linux</td>
	  <td class="lt-lr" align="center">Supported</td>
	  <td class="lt-r" align="center">Supported</td>
	  <td class="lt-r" align="center">N/A</td>
	  <td class="lt-" align="center">N/A</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">x86_64, FreeBSD</td>
	  <td class="lt-lr" align="center"></td>
	  <td class="lt-r" align="center">Supported</td>
	  <td class="lt-r" align="center">N/A</td>
	  <td class="lt-" align="center">N/A</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">x86 (32 bit), Linux</td>
	  <td class="lt-lr" align="center">Supported</td>
	  <td class="lt-r" align="center">Supported</td>
	  <td class="lt-r" align="center"></td>
	  <td class="lt-" align="center">N/A</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">AArch64, macOS</td>
	  <td class="lt-lr" align="center">Supported</td>
	  <td class="lt-r" align="center">Supported</td>
	  <td class="lt-r" align="center">N/A</td>
	  <td class="lt-" align="center">N/A</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">AArch64, Android</td>
	  <td class="lt-lr" align="center"></td>
	  <td class="lt-r" align="center"><a class="underlined" href="1-user-guide#cross">Preliminary</a></td>
	  <td class="lt-r" align="center">N/A</td>
	  <td class="lt-" align="center">N/A</td>
	</tr>
	<tr>
	  <td class="lt-br" align="left">AArch64, iOS</td>
	  <td class="lt-blr" align="center"></td>
	  <td class="lt-br" align="center"><a class="underlined" href="1-user-guide#cross">Preliminary</a></td>
	  <td class="lt-br" align="center">N/A</td>
	  <td class="lt-b" align="center">N/A</td>
	</tr>
	<tr>
	  <td class="lt-r" align="left">RISC-V (64-bit), Linux</td>
	  <td class="lt-lr" align="center">Supported</td>
	  <td class="lt-r" align="center">Supported</td>
	  <td class="lt-r" align="center">N/A</td>
	  <td class="lt-" align="center">N/A</td>
	</tr>
      </table>
    </td>
  </tr>
</table>

<div style="margin-top: 2.0cm;"></div>

<p>
  The supported compiler versions are as follows.
</p>

<div><br/></div>

<ul class="disc">
  <li>GCC : version 5 and later</li>
  <li>Clang : version 6 and later</li>
  <li>Intel Compiler : ICC version 17</li>
  <li>MSVC : Visual Studio 2019</li>
</ul>

<div><br/></div>

<p>
  *1 NEON has only single precision support. The computation results
  are not in full accuracy because NEON is not IEEE 754-compliant.
</p>

<p>
  *2 LTO is not supported.
</p>

<p>
  *3 AVX functions are not supported for Cygwin, because AVX is not
  supported by Cygwin ABI.
  SLEEF also builds with MinGW for Windows on x86, but only DFT can
  be tested for now.
</p>

<p>
  *4 Some compiler versions simply do not support certain vector
  extensions, for instance SVE is only supported for gcc version 9
  onwards. Similarly, the RISC-V interface in SLEEF is based on
  version 1.0 of the intrinsics, which is only supported from llvm
  version 17 and gcc version 14 onwards. Toolchain files provide
  some information on supported compiler versions.
</p>


<div style="margin-top: 1.0cm;"></div>

<p>
  All functions in the library are thread safe unless otherwise noted.
</p>
  

<h2 id="credit">Credit</h2>

<ul class="disc">
  <li>The main developer is <a class="underlined"
  href="https://github.com/shibatch">Naoki Shibata</a>
  ( <a href="mailto:shibatch@users.sourceforge.net">shibatch@users.sourceforge.net</a> )
  at Nara Institute of Science and Technology.</li>
  <li><a class="underlined"
  href="https://github.com/blapie">Pierre Blanchard</a>,
  at Arm Ltd. is the current global maintainer for SLEEF, alongside
  <a class="underlined"
  href="https://github.com/joanaxcruz">Joana Cruz</a> and
  <a class="underlined"
  href="https://github.com/joeramsay">Joe Ramsay</a>.</li>
  <li><a class="underlined"
  href="https://github.com/luhenry">Ludovic Henry</a>
  at Rivos Inc. participated in adding support for RISC-V vector extensions
  as well as CI tests based on Github Actions.</li>
  <li><a class="underlined"
  href="https://github.com/fpetrogalli">Francesco Petrogalli</a>
  at ARM Ltd. contributed the helper for AArch64 (helperadvsimd.h,
  helpersve.h) and GNUABI interface of the library. He also worked on
  migrating the build system to CMake, and reviewed the code, gave
  precious comments and suggestions.</li>
  <li><a class="underlined" href="https://github.com/hfinkel">Hal Finkel</a>
  at Argonne Leadership Computing Facility is now working
  on <a class="underlined"
  href="https://reviews.llvm.org/D24951">importing and adapting SLEEF
  as an LLVM runtime</a>. He also gave precious comments.</li>
  <li><a class="underlined" href="https://github.com/diaena">Diana
  Bite</a> at University of Manchester and <a class="underlined"
  href="https://github.com/xoofx">Alexandre Mutel</a> at Unity
  Technologies worked on migrating the build system to
  CMake.</li>
  <li><a class="underlined" href="https://github.com/blu">Martin
  Krastev</a> at Chaos Group contributed faster implementation of fmin
  and fmax functions.</li>
  <li><a class="underlined" href="https://github.com/cdluminate">Mo Zhou
  </a> is managing packages for <a class="underlined"
  href="https://tracker.debian.org/pkg/sleef">Debian</a>
  and <a class="underlined"
  href="https://launchpad.net/~lumin0/+archive/ubuntu/sleef">Ubuntu
  PPA</a>.</li>
  <li><a class="underlined"
  href="https://github.com/shibatch/sleef/graphs/contributors">
  And many more contributors you can find listed on GitHub.</a></li>
</ul>

<h2 id="partners">Partner institutes and corporations</h2>

|               |                   |
|:-------------:|:------------------|
| [![NAIST logo](img/naistlogo.svg)](https://www.naist.jp/en/) | Division of Information Science of Nara Institute of Science and Technology participates through Naoki Shibata. |
| [![IBM logo](img/IBM_logo.svg)](https://ibm.com) | As the leading company in a wide range of information technologies, <a class="underlined" href="https://ibm.com/">IBM</a> participates through David Edelsohn. |
| [![ARM logo](img/Arm-logo-blue-pms313.svg)](https://www.arm.com) | As the leading IP company in semiconductors design, <a class="underlined" href="https://www.arm.com/">ARM</a> participates through Pierre Blanchard, Joe Ramsay and Joana Cruz. |
| [![Unity Technologies logo](img/Unity_Technologies_logo.svg)](https://unity3d.com) | As the leading company in developing a video game engine, <a class="underlined" href="https://unity3d.com/">Unity Technologies</a> participates through Alexandre Mutel. |

<h2 id="license">License</h2>

|               |                   |
|:-------------:|:------------------|
| [![open source logo](img/osi_logo.png)](https://opensource.org) | Boost Software License is <a class="underlined" href="https://opensource.org/licenses/BSL-1.0">OSI-certified</a>. </br> See <a class="underlined" href="http://www.boost.org/users/license.html">this page</a> for more information about Boost Software License. |

<h2 id="history">History</h2>

<p class="noindent" style="margin-top: 1.0cm;">
See <a class="underlined"
href="https://github.com/shibatch/sleef/blob/master/CHANGELOG.md">Changelog</a>
for a full history of changes to SLEEF.</p>

<h2 id="related">Related projects and links</h2>

<ul class="disc">
  <li>SLEEF is adopted in <a class="underlined"
  href="https://youtu.be/QkM6zEGFhDY?t=2328">the Burst Compiler in
  Unity</a>, and also in
  the <a class="underlined" href="https://youtu.be/WnJV6J-taIM?t=426">Android
  version</a>.</li>
  <li>SLEEF is now included in <a class="underlined"
  href="https://developer.arm.com/documentation/101458/1930/Vector-math-routines/Vector-math-routines-in-Arm-C-C---Compiler">
  Arm Compiler for HPC</a>.</li>
  <li>SLEEF is adopted in <a class="underlined"
  href="https://github.com/pytorch/pytorch/pull/6725">PyTorch</a>.</li>
  <li>SLEEF is adopted in <a class="underlined"
  href="https://docs.nvidia.com/cuda/cublas/index.html#appendix-acknowledgements">NVIDIA cuBLAS</a>.</li>
  <br/>

  <li>SLEEF is adopted in the following projects.
    <ul class="circle">
      <li><a href="https://github.com/musm/SLEEF.jl">A pure Julia port
	  of the SLEEF math library</a></li>
      <li><a href="https://docs.rs/crate/sleef-sys/">A Rust FFI
	  bindings to SLEEF</a></li>
      <li><a href="http://www.menuetos.net/sc151.html">MenuetOS</a></li>
      <li><a href="https://github.com/Beep6581/RawTherapee/tree/dev/rtengine">RawTherapee</a></li>
      <li><a href="http://buraphakit.sourceforge.net/BASIC.shtml">John's ECMA-55 Minimal BASIC Compiler</a></li>
      <li><a href="https://github.com/pocl/pocl/tree/master/lib/kernel/sleef">Portable Computing Language(pocl)</a></li>
      <li><a href="https://github.com/cdl-saarland/rv">The Region Vectorizer(Compiler Design Lab at Saarland University)</a></li>
      <li><a href="https://agenium-scale.github.io/nsimd">Agenium Scale NSIMD</a></li>
      <li><a href="https://code.jsoftware.com/wiki/System/ReleaseNotes/J902">J Language</a></li>
      <li><a href="https://github.com/simd-everywhere/simde">SIMD Everywhere</a></li>
      <li><a href="https://github.com/dnbaker/minocore">Minocore</a></li>
      <li><a href="https://github.com/greatest-ape/OctaSine">OctaSine</a></li>
      <li><a href="https://github.com/jackmott/simdeez">Simdeez</a></li>
   </ul>
  </li>
</ul>

<h2 id="publication">Publication</h2>

<ul class="disc">
  <li>Naoki Shibata and Francesco Petrogalli : <B>SLEEF: A Portable Vectorized Library of C Standard Mathematical Functions,</B> <I>in IEEE Transactions on Parallel and Distributed Systems,</I> <a class="underlined" href="https://doi.org/10.1109/TPDS.2019.2960333">DOI:10.1109/TPDS.2019.2960333</a> (Dec. 2019). [<a class="underlined" href="https://arxiv.org/pdf/2001.09258">PDF</a>]</li>
  <li>Francesco Petrogalli and Paul Walker : <B>LLVM and the automatic vectorization of loops invoking math routines: -fsimdmath</B>, <I>2018 IEEE/ACM 5th Workshop on the LLVM Compiler Infrastructure in HPC (LLVM-HPC), pp. 30-38.,</I> <a class="underlined" href="https://doi.org/10.1109/LLVM-HPC.2018.8639354">DOI:10.1109/LLVM-HPC.2018.8639354</a> (Nov. 2018). [<a class="underlined" href="https://sc18.supercomputing.org/proceedings/workshops/workshop_files/ws_llvmf106s2-file1.pdf">PDF</a>]</li>
</ul>

