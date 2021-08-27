---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

Title: "Verifying the Mathematical Library of a UAV
Autopilot with Frama-C"
event: "FMICS 2021"
location: "Videoconference" 
abstract: "Ensuring safety of critical systems is crucial and is often attained
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
  interesting functional properties on floating-point conversion functions."

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: 2021-08-24T14:30:00
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
url_slides: "uploads/afadl-2021-presentation.pdf"

url_code:
url_pdf:
url_video: "https://youtu.be/R8hmYKCchLk?t=1670"

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
projects: ["paparazzi-frama-c"]
---

