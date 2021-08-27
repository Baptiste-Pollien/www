---
title: "Verifying the Mathematical Library of a UAV
Autopilot with Frama-C"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin
- cgarion
- ghattenberger
- proux
- xthirioux

date: "2021-07-01T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2021-07-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: "In *Formal Methods for Industrial Critical Systems 2021*"
publication_short: "In *FMICS 2021*"

abstract: Ensuring safety of critical systems is crucial and is often attained
  by extensive testing of the system. Formal methods are now commonly
  accepted as powerful tools to obtain guarantees on such systems,
  even if it is generally not possible to formally prove the safety
  and correctness of the whole system. This paper presents an
  ongoing work on the formal verification of the
  [Paparazzi](https://wiki.paparazziuav.org/wiki/Main_Page) UAV
  autopilot using the Frama-C verification platform. We focus on a
  Paparazzi mathematical library providing different UAV state
  representations and associated conversion functions and manage to
  prove the absence of runtime errors in the library and some
  interesting functional properties on floating-point conversion functions.

# Summary. An optional shortened abstract.
summary:  Ensuring safety of critical systems is crucial and is often attained
  by extensive testing of the system. Formal methods are now commonly
  accepted as powerful tools to obtain guarantees on such systems,
  even if it is generally not possible to formally prove the safety
  and correctness of the whole system. This paper presents an
  ongoing work on the formal verification of the
  [Paparazzi](https://wiki.paparazziuav.org/wiki/Main_Page) UAV
  autopilot using the Frama-C verification platform. We focus on a
  Paparazzi mathematical library providing different UAV state
  representations and associated conversion functions and manage to
  prove the absence of runtime errors in the library and some
  interesting functional properties on floating-point conversion functions.

tags: ["Proof of program", "Critical systems", "Deductive methods", "Abstract
interpretation"]

# Display this page in the Featured widget?
featured: false

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'uploads/fmics-2021.pdf'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: 'uploads/fmics-2021-presentation.pdf'
url_source: ''
url_teaser: 'https://youtu.be/zwXIsqcOlYM'
url_video: 'https://youtu.be/R8hmYKCchLk?t=1670'

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
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
