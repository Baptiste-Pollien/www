---
title: Formal verification of the Paparazzi autopilot
summary: Verification of a mathematical library using Frama-C.
tags:
- Frama-C
- Paparazzi
date: "2021-05-27T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Photo by rawpixel on Unsplash
  focal_point: Smart

links:
- icon: gitlab
  icon_pack: fab
  name: Repository
  url: https://gitlab.isae-supaero.fr/b.pollien/paparazzi-frama-c
- icon: wikipedia-w
  icon_pack: fab
  name: Paparazzi
  url: https://wiki.paparazziuav.org/wiki/Main_Page
- icon: github
  icon_pack: fab
  name: Paparazzi
  url: https://github.com/paparazzi/paparazzi
  
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---

This project is a fork of Paparazzi UAV autopilot repository
(https://github.com/paparazzi/paparazzi). The aim of this project is
to verify the `pprz_algebra` library using Frama-C.

The GitLab project adds ACSL annotations and provides a script to
automatically launch Frama-C. Frama-C analyses the code, checks for
the absence of RTE (_RunTime Errors_) and verify some functional
properties.

Required software
-----------------
To run the verification, the following software are required:

- Frama-C, a compiled version from
[source](https://git.frama-c.com/pub/frama-c) using commit `3fa7de0c`
- Alt-Ergo 2.3.3
- CVC4 1.9-prerelease
- Z3 4.8.6
- Coq 8.12.2
- Why3 1.3.3
- ctags

**Note:** This specific version of Frama-C is needed because it
fixes a bug that prevented proving some goals. Also, the
_statement contracts_ are used in the proofs, but this feature
has been removed in newer versions.

How to launch the verification process
--------------------------------------

First, go to the `sw/airborne` directory:

```
cd sw/airborne
```

Update the variable `FRAMAC_PREFIX` in `frama-c-analysis.sh`
with the path of the directory containing Frama-C binary. Then,
launch the script that starts the analysis:

```
./frama-c-analysis.sh
```

The WP smoke tests can be enabled with the environment variable
`SMOKE` as follows:

```
SMOKE=1 ./frama-c-analysis.sh
```

Quick description of modified files
------------------------------------

- `sw/airborne/frama-c-analysis.sh`: a shell script that automatically
launches the verification using Frama-C.
- `sw/airborne/output-frama-c-analysis.sh`: a Python script used by
`frama-c-analysis.sh` to read and analyse the results from Frama-C.
- `sw/airborne/math/pprz_algebra_(int|float|double).(h|c)`: the
mathematical library of Paparazzi that has been verified. These files
have been annotated with ACSL.
- `sw/airborne/math/pprz_algebra_(int|float|double)_frama_c.h`: files
containing definition of predicates, lemmas and logical functions used
to verify the absence of RTE in the library.
- `sw/airborne/math/pprz_algebra_float_convert_rmat_frama_c.h`:
definition of predicates, lemmas and logical functions for the
verification of functional properties.
- `sw/airborne/.frama-c/wp/interactive`: Coq scripts containing the
proof lemmas.
- `sw/airborne/.frama-c/wp/script`: WP scripts containing the tactics
used to prove some goals.

Verification process
---------------------

The verification process combines the analysis of the
[EVA](https://frama-c.com/fc-plugins/eva.html) and
[WP](https://frama-c.com/fc-plugins/wp.html) plugins of Frama-C. The
EVA plugin requires a program entry point (a `main` or a function) to
start its analysis. The script `frama-c-analysis.sh` finds
automatically all the names of the functions in the library using
ctags. Then, verification is launched for every function `FUNCTION`
with the following parameters:

- `-rte`: adds RTE annotations in the code.
- `-no-warn-left-shift-negative`: allows left shift for negative values.
- `-eva -lib-entry -main $FUNCTION`: launches EVA analysis with
`$FUNCTION` as the entry point. The initial state is determined by
the _preconditions_ specified in the contract of the function.
- `-wp-fct $FUNCTION`: launches the WP verification with the following
  options:
  - `-wp-cache update`: enables and uses cache.
  - `-wp-model real+Cast`: enables the `real` model to represent the
  arithmetic on floating-point numbers. The `Cast` option enables the
  usage of cast in the code.
  - `-wp-prover alt-ergo,cvc4-strings-ce,z3,z3-ce,z3-nobv,tip`:
  adds the different provers needed to verify the goals.
- `-cpp-extra-args=-I../include`: adds the include directory of
  Paparazzi.
- `-cpp-extra-args=-DFRAMA_C_ANALYSIS`: defines a C constant in order
  to remove certain portions of code that are not supported by
  Frama-C.

<!-- Quick link to functions described in FMICS 2021 paper
-----------------------------------------------------

- the
  [`float_rmat_of_quat`](https://gitlab.isae-supaero.fr/b.pollien/paparazzi-frama-c/-/blob/fmics-2021/sw/airborne/math/pprz_algebra_float.h#L633)
  function
- the
  [`float_quat_of_rmat`](https://gitlab.isae-supaero.fr/b.pollien/paparazzi-frama-c/-/blob/fmics-2021/sw/airborne/math/pprz_algebra_float.h#L946)
  function
- the
  [`float_rmat_of_eulers_321`](https://gitlab.isae-supaero.fr/b.pollien/paparazzi-frama-c/-/blob/fmics-2021/sw/airborne/math/pprz_algebra_float.h#L612)
  function
- the
  [`float_rmat_of_eulers_312`](https://gitlab.isae-supaero.fr/b.pollien/paparazzi-frama-c/-/blob/fmics-2021/sw/airborne/math/pprz_algebra_float.h#L620)
  function -->


More information about Paparazzi
--------------------------------

To have information about Paparazzi, go directly on the
[website](https://wiki.paparazziuav.org/wiki/Main_Page) or on the
[GitLab project](https://github.com/paparazzi/paparazzi).

