---
title: Study of virtual element method (VEM)
summary: Virtual element method (VEM) is considered as as general finite element method because it can be used for any arbitrary polygon meshes. 
tags:
- virtual element method
- Flexible mesh
- Hanging node
- Computational mechanics
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
<font size="4" font face = "Times New Roman">
<DIV align="justify">
  Virtual element method (VEM), which is recently proposed by L. Beirão da Veiga [1], is well-developed since its birth and becomes a powerful tool in the field of computational mechanics. Different from classical finite element method (FEM), VEM has the following features
  <ul>
  <li> VEM can be applied to arbitrary polygonal mesh </li>
  <li> VEM is able to handle hanging nodes on element edge </li>
  </ul>  
A number of researches are implemented to  exploit the effectiveness and application of VEM, including elastic analysis [2], finite deformation analysis[3], contact analysis [4], fracture analysis [5] and structural topology optimization [6]. Based on Ref. [4], the study contact analysis with non-matching contact interface by using second-order VEM is investigated. The results show that even with irregular element shape and non-matching interface, the patch test is passed as shown in Figs.1-2. Moreover, and the accuracy of the VEM is also satisfied when compared to the results obtained by ABAQUS as shown in Fig.2.
</DIV>
  <img src="VEM-2.png" style="width: 50%; height: 50%" />
  <img src="VEM-3.png" style="width: 50%; height: 50%" syle = "float:left" />
  
<font size="4" font face = "Times New Roman">
<DIV align="center">
  
</DIV> 
