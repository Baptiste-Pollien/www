---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

Title: "Formal Verification of an UAV autopilot: Static analysis and Verified Code Generation"
event: "Thesis Defense"
location: "ISAE-SUPAERO - Toulouse, FRANCE" 
abstract: "
Ensuring safety of critical systems is crucial and is often attained by extensive testing of the system. Formal methods are now
commonly accepted as powerful tools to obtain guarantees on such systems, even if it is generally not possible to formally prove the
safety and correctness of the whole system. This thesis deals with the formal verification of some software components of an
autopilot. These components have been selected according to their criticality and should therefore be correct by construction and/or
by verification. The goal of this thesis is first to review the formal verification and program proof methods that can be applied to such
software in order to apply them on these components of the Paparazzi autopilot developed at ENAC. This thesis also aims to see if
the analysis process using such techniques and associated tools can be applied on projects that already exist and are not designed
for the verification tools. This thesis focuses on two techniques for the verification of two specific components of Paparazzi.

The first component is a Paparazzi mathematical library verified using the Frama-C platform. This library provides different UAV state
representations and associated conversion functions that are used by the drone control system in order to take flight decisions.
The Frama-C platform is used with the WP, EVA and RTE plugins to verify the absence of runtime errors in the library and some
interesting functional properties on floating-point conversion functions. This verification work required the specification of the
correctness properties in the form of function contracts (pre and post condition). The majority of the contracts were automatically
verified by the SMT solvers except for some functional properties that must be manually helped using the Coq proof assistant.

The second component verified is a flight plan generator. Paparazzi has a domain specific language called FPL, used to specify
flight plans. It is a programming and modelling language allowing the expression of complex missions. FPL missions are compiled
into C code that is directly embedded into the autopilot code. The FPL to C code generator, currently written in OCaml, is therefore a
critical component when addressing the drone safety. This thesis formally verifies the FPL compilation process. First, three-pass
code generator, targeting the Clight intermediate language from the CompCert suite has been developed in Coq. Then, an
operational semantics have been formally defined. Finally, the generator has been formally verified by manually proving a
bisimulation relation between FPL semantics and Clight semantics. In the course of the formalization and verification process, we
have also unveiled several problems in the original Paparazzi code generator."

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: 2023-11-16T10:00:00
date_end: 
all_day: false

authors: 
- admin
tags: []

# Is this a featured talk? (true/false)
featured: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

# Optional filename of your slides within your talk's folder or a URL.
url_slides: "uploads/thesis-presentation.pdf"

url_code:
url_pdf:
url_video: ""

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects:
- vpfg
- paparazzi-frama-c
---

