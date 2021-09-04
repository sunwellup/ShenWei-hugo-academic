---
title: Investigation of virtual element method (VEM)
summary: Virtual element method (VEM) is considered as as general finite element method because it can be used for any arbitrary polygon meshes. 
tags:
- virtual element method
- Contact problem
- Elasticity
- small and finite deformations
date: "2021-08-30T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Benchmark test with L-shaped element using VEM
  focal_point: Smart

links:
# - icon: twitter
#  icon_pack: fab
#  name: Follow
#  url: https://twitter.com/georgecushen
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
<DIV align="justify">
The main idea of VEM is to project the function in virtual element space (i.e., the space of shape functions) to a polynomial space with predefined order. For example, consider a standard boundary problem with a domain **\Omega** 

<DIV align="justify"> 
  
  
{{< figure src="VEM-1.png" title="DOFs of second-order VEM" numbered="true" >}}

