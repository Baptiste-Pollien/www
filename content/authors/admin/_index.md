---
# Display name
title: Baptiste Pollien, PhD

# Is this the primary user of the site?
superuser: true

# Role/position/tagline
role: Software Engineer HMI

# Organizations/Affiliations to show in About widget
organizations:
- name: Ampere Software Technology
  url: https://www.ampere.cars/

# Short bio (displayed in user profile at end of posts)
bio: I am a Software Engineer HMI at Ampere Software Technology.

# Interests to show in About widget
interests:
- Formal Methods
- Rust
- Critical Systems
- Automotives
- Coq

# Education to show in About widget
education:
  courses:
  - course: PhD in Formal Methods
    institution: ISAE-SUPAERO - Toulouse, FRANCE
    year: 2023 - 2020
  - course: Master’s Degree in Engineering
    institution: ENSIMAG - Grenoble, FRANCE
    year: 2020 - 2017
  - course: Preparation for entry to engineering schools
    institution: Univ. Grenoble Alpes - Grenoble, FRANCE
    year: 2017 - 2015

# Social/Academic Networking
# For available icons, see: https://wowchemy.com/docs/getting-started/page-builder/#icons
#   For an email link, use "fas" icon pack, "envelope" icon, and a link in the
#   form "mailto:your-email@example.com" or "/#contact" for contact widget.
social:
- icon: envelope
  icon_pack: fas
  link: '/#contact'
- icon: google-scholar  # Alternatively, use `google-scholar` icon from `ai` icon pack
  icon_pack: ai
  link: https://scholar.google.com/citations?user=1tYQFOAAAAAJ&hl=fr
- icon: github
  icon_pack: fab
  link: https://github.com/Baptiste-Pollien
- icon: linkedin
  icon_pack: fab
  link: https://www.linkedin.com/in/baptiste-pollien
- icon: gitlab
  icon_pack: fab
  link: https://gitlab.isae-supaero.fr/b.pollien

# Link to a PDF of your resume/CV.
# To use: copy your resume to `static/uploads/resume.pdf`, enable `ai` icons in `params.toml`, 
# and uncomment the lines below.
# - icon: cv
#   icon_pack: ai
#   link: uploads/resume.pdf

# Enter email to display Gravatar (if Gravatar enabled in Config)
email: "baptiste.pollien@renault.com"

# Highlight the author in author lists? (true/false)
highlight_name: false
---

I am a Software Engineer HMI at [Ampere Software Technology](https://www.ampere.cars/), working on the [Software Defined Vehicle](https://www.renaultgroup.com/news-onair/actualites/tout-savoir-sur-le-software-defined-vehicle/) (SDV) project.

I defended my thesis in November 2023, [Formal Verification of an UAV autopilot: Static analysis and Verified Code Generation](https://baptiste-pollien.fr/uploads/Baptiste_Pollien_thesis.pdf). My thesis deals with formal methods applied on UAV autopilot, especially [Paparazzi](https://wiki.paparazziuav.org/wiki/Main_Page) autopilot developed at [ENAC](https://www.enac.fr/). I worked on the verification of a mathematical library of Paparazzi using [Frama-C](https://frama-c.com/) with [EVA](https://frama-c.com/fc-plugins/eva.html) and [WP](https://frama-c.com/fc-plugins/wp.html) plugins. I focused on the verification of the absence of runtime errors (overflows, divisions by 0…) but I also verified some functional properties. I also worked on the verification of the Paparazzi flight plan generator using [Coq](https://coq.inria.fr/). I formalised the flight plan semantics of the input language and I have proved the correctness of the generator.

<!-- {{< icon name="download" pack="fas" >}} Download my {{< staticref "uploads/demo_resume.pdf" "newtab" >}}resumé{{< /staticref >}}. -->
