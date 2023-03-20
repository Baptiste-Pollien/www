---
title: VFPG
summary: Verified Flight Plan Generator in Coq.
tags:
- Coq
- CompCert
- Paparazzi
date: "2021-11-08T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Photo by rawpixel on Unsplash
  focal_point: Smart

links:
- icon: gitlab
  icon_pack: fab
  name: Repository
  url: https://gitlab.isae-supaero.fr/b.pollien/vfpg
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

# VFPG: Verified Flight Plan Generator

**VFPG** is a generator of flight plan developed in Ocaml and Coq. The
generator takes as input an XML describing a flight plan and it
generates a C code that can be compiled and embedded on a drone.

This project is mainely designed to work with the Paparazzi UAV autopilot
<https://github.com/paparazzi/paparazzi>. However, the generator has a
modular architecture that can be adapted to easily support other
autopilots.

## Dependencies

* [Coq](https://coq.inria.fr) (tested with version 8.15)
* [OCaml](https://github.com/ocaml/ocaml) (tested with version 4.13.1)
* [OCamlbuild](https://github.com/ocaml/ocamlbuild) (tested with version 0.14.1)
* [xml-light](https://github.com/ncannasse/xml-light) (tested with version 2.4)
<!-- * [CompCert](https://github.com/AbsInt/CompCert) (tested with version 3.9)

You can install all dependencies using [OPAM](https://opam.ocaml.org)
(version 2.0 or later):

```bash
opam repo add coq-released https://coq.inria.fr/opam/released
opam update
opam install menhir.20211012 coq-compcert.3.9 xml-light
``` -->

MathComp is required and can be installed using [OPAM](https://opam.ocaml.org)
(version 2.0 or later):

```bash
opam repo add coq-released https://coq.inria.fr/opam/released
opam install coq-mathcomp-ssreflect
```

## Using the Generator

The project needs the source of
[Paparazzi](https://github.com/paparazzi/paparazzi) and
[CompCert](https://github.com/AbsInt/CompCert)@9d3521b4. The sources must
be modified and compiled in order to use the generator. These steps can be
easily retrieved with the following script.

```bash
./configure
```

The generator can then be built using the Makefile.

```bash
make build
```

The description of the build process is described [here](https://gitlab.isae-supaero.fr/b.pollien/vfpg/-/blob/master/docs/build.md)

The generator can then be used with the following command:

```bash
./vfpg.native [XML input file] [C output file]
```

The Makefile can also launch tests.

```bash
make tests
```

All the tests available are described [here](https://gitlab.isae-supaero.fr/b.pollien/vfpg/-/blob/master/docs/tests.md)

It is also possible to test the Clight generator using the command:

```bash
make CommonFP
```

This command will use `CompCert` to generate a Clight version of the file
`common-c-code/common_flight_plan.c` (saved in the file
`generated/CommonFP.v`). This file is then converted into C code using the
CompCert printer. The result is written in `out/common_flight_plan.h` file.

## Description of folders in the project

* `common-c-code`: The common C code for all the flight plan.
* `docs`: The documentation of the project.
* `frontend`: The frontend Ocaml code for the generator.
* `generated`: The Clight files generated with `clightgen`. They are stored as
   they are used in Coq proofs.
* `ocaml-generator`: The Ocaml code of the previous Flight Plan generator of
Paparazzi. This code has been extracted from the whole Paparazzi project for
testing purpose. In this folder you can find:
  * The folder `src` containing the main source of the previous generator.
  * The folder `src_paparazzi` that contains all the libraries needed by the
  generator.
  * The script `run.sh` that build and run the generator. It will produce in
    the `out` folder the C flight plan corresponding to `examples/new_features.xml`.
* `src`: All the Coq sources of the generator. A description of these files can be found [here](https://gitlab.isae-supaero.fr/b.pollien/vfpg/-/blob/master/docs/coq-descr-files.md).
* `tests`: The scripts that launch all tests described [here](https://gitlab.isae-supaero.fr/b.pollien/vfpg/-/blob/master/docs/tests.md).
* `tools`: Script use during the [build process](https://gitlab.isae-supaero.fr/b.pollien/vfpg/-/blob/master/docs/build.md)

## Generate Coq Doc

```bash
make doc
firefox html/toc.html
```

A description of all Coq files can be found [here](https://gitlab.isae-supaero.fr/b.pollien/vfpg/-/blob/master/docs/coq-descr-files.md).

## New Features added

* Forbidden deroute: Possibility to forbid certain deroute between blocks.
* The filed `on_enter` and `on_exit` has been added for the blocks.
* Height added to the oval (not added everywhere)
* Return an errors if a flight plan contains more thant 256 blocks or stages.

## Current Limitations

Currently, all the features are not implemented and some modifications from
the original flight plan generator has been made:

* When a C code is used for a condition, we considered that the
  execution return an integer value, evaluated as a boolean (returned value
  are converted into 0 or 1 only).
* The parameter `last_wp` is a string.
* Exceptions and forbidden deroute in loops are ignored.
* `on_enter` option do not work for the first block.
* If the next block is forbidden then the execution state does not change.
* If there is an exception but the block is forbidden, then no deroute will
  occur.
* The field `exec` must be an instruction.
* The constant `NB_BLOCK` has been replaced by constant variables.
* When there is a deroute, the current stage is not changed. In the case
  of a return, we jump in the deroute stage.
* TODO: The proof uses a simplified version of the whole CommonFP.

## More information about Paparazzi

To have information about Paparazzi, go directly on the
[website](https://wiki.paparazziuav.org/wiki/Main_Page) or on the
[GitLab project](https://github.com/paparazzi/paparazzi).
