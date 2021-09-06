---
title: Investigation of virtual element method (VEM)
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
  
  <br/>
  
  <ul>
  <li> $ \boldsymbol{v}_h $ is continuous on the boundary of element <i>K</i> </li>
  <li> $ \boldsymbol{v}_h $ is a vector with second-order polynomial components on each edge of element <i>K</i> </li>
  <li> $ \Delta \boldsymbol{v}_h $ is a vector with second-order polynomial components on each edge of element <i>K</i> </li> 
  </ul>  
where $ \Delta $ is the Laplace operator. <b> The corresponding DOFs of element <i>K</i> can be classified into the following three types </b>
  <ol style="list-style-type:lower-roman">
    <li> The values of $ \boldsymbol{v}_h $ at the 5 vertices of element <i>K</i> </li>
    <li> The values of $ \boldsymbol{v}_h $ at the 5 midpoints of 5 edges of element <i>K</i> </li>
    <li> The two moments of $ \boldsymbol{v}_h $ with respect to the constant vectors $ \boldsymbol{p}_1=[1,0]^T $ and $ \boldsymbol{p}_2=[0,1]^T $ in element <i>K</i>, that is 
  
</DIV> 
