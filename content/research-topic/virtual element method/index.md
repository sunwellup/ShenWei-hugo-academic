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
  <b> b <b>
  VEM is a recently proposed numerical discretization technique in Galerkin framework which is inspired by mimic finite difference (MFD) method, and since the date of birth it has been extensively developed and applied to a wide range of engineering problems. The core of the method is to construct a projector which projects the function in local virtual element space (or say, local shape function space) to a polynomial space with prescribed order. In this way VEM avoids the explicit construction of shape function and its integral over the element domain; and thus VEM is able to handle arbitrary polygonal mesh. 
</DIV>   
<DIV align="justify"> 
  In order to give a simple and general illustration of how VEM works, here I take a linear elasticity boundary value problem in 2-dimensional domain **$\Omega$** as example. The domain is partitioned into arbitrary polygonal meshes *T_h*, and suppose one of the element is pentagon as shown in Fig. 1. <strong>b<strong>
  
</DIV> 
  
  
{{< figure src="VEM-1.png" title="DOFs of second-order VEM" numbered="true" >}}

