---
title: "Formal Verification of an UAV autopilot: Static analysis and Verified Code Generation"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin

date: "2023-11-16T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2023-11-16T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: "Thesis"
publication_short: ""

abstract: "Critical systems are systems whose failure could have catastrophic consequences, such as the destruction of expensive equipment or the death of people. These systems are found in the automotive, medical and drone autopilot systems. It is essential to ensure that these systems do not present a risk of failure. Formal methods are powerful verification techniques for obtaining strong guarantees on such systems, even if it is generally not possible to formally verify the entire system. This thesis deals with the formal verification of certain critical software components
of a drone autopilot. It made it possible to review different methods of verification and proof of programs that can be applied to such software and use them on a case study, the Paparazzi autopilot developed at ENAC."

# Summary. An optional shortened abstract.
summary:  "Ensuring safety of critical systems is crucial and is often attained by extensive testing of the system. Formal methods are now commonly accepted as powerful tools to obtain guarantees on such systems, even if it is generally not possible to formally prove the safety and correctness of the whole system. This thesis deals with the formal verification of some software components of an
autopilot. These components have been selected according to their criticality and should therefore be correct by construction and/or
by verification. The goal of this thesis is first to review the formal verification and program proof methods that can be applied to such software in order to apply them on these components of the Paparazzi autopilot developed at ENAC. This thesis also aims to see if the analysis process using such techniques and associated tools can be applied on projects that already exist and are not designed
for the verification tools. This thesis focuses on two techniques for the verification of two specific components of Paparazzi.


The first component is a Paparazzi mathematical library verified using the Frama-C platform. This library provides different UAV state representations and associated conversion functions that are used by the drone control system in order to take flight decisions.
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


tags: ["Formal methods", "Verification and validation",
"Cyberphysical systems", "Proof of program", "Mechanized proof", "Static analysis"]

# Display this page in the Featured widget?
featured: false

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'uploads/Baptiste_Pollien_thesis.pdf'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: 'uploads/thesis-presentation.pdf'
url_source: ''
url_teaser: ''
url_video: ''

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
- vfpg
- paparazzi-frama-c

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

<!-- {{% callout note %}}
Click the *Cite* button above to demo the feature to enable visitors to import publication metadata into their reference management software.
{{% /callout %}}

{{% callout note %}}
Create your slides in Markdown - click the *Slides* button to check out the example.
{{% /callout %}}

Supplementary notes can be added here, including [code, math, and images](https://wowchemy.com/docs/writing-markdown-latex/). -->
