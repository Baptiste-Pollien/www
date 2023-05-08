---
title: "A Verified UAV Flight Plan Generator"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin
- cgarion
- ghattenberger
- proux
- xthirioux

date: "2023-02-02T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2023-02-02T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: "In the *International Conference on Formal Methods in Software Engineering 2023*"
publication_short: "In *FormaliSE 2023*"

abstract: FPL is a domain specific language used to specify complex drone
  missions for the Paparazzi open-source autopilot. FPL missions are
  compiled into C code that is directly embedded into the autopilot
  code. The FPL to C code generator, currently written in OCaml, is
  therefore a critical component when addressing the drone safety. This
  paper presents the formal verification of the FPL compilation
  process. First, we have developed in Coq a new three-pass code
  generator, targeting the Clight intermediate language from the
  CompCert suite. We have then formally defined an operational
  semantics for FPL. Finally, we have proved a bisimulation relation
  between FPL semantics and Clight semantics. In the course
  of the formalization and verification process, we have also unveiled
  several problems in the original Paparazzi code generator.

# Summary. An optional shortened abstract.
summary:  FPL is a domain specific language used to specify complex drone
  missions for the Paparazzi open-source autopilot. FPL missions are
  compiled into C code that is directly embedded into the autopilot
  code. The FPL to C code generator, currently written in OCaml, is
  therefore a critical component when addressing the drone safety. This
  paper presents the formal verification of the FPL compilation
  process. First, we have developed in Coq a new three-pass code
  generator, targeting the Clight intermediate language from the
  CompCert suite. We have then formally defined an operational
  semantics for FPL. Finally, we have proved a bisimulation relation
  between FPL semantics and Clight semantics. In the course
  of the formalization and verification process, we have also unveiled
  several problems in the original Paparazzi code generator.

tags: ["Code Generation", "Compilation", "Mechanized proof", "Operational semantics"]

# Display this page in the Featured widget?
featured: false

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

# TODO 
url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: 'uploads/formalise-2023-presentation.pdf'
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
