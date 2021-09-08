---
title: Shape and topology optimization of plane frame
summary: Compared to ground structure method, simultaneous shape and topology optimization can start from a rather sparse initial structure where not all the possible connections among the nodes are needed.
tags:
- Shape and topogy optimization of plane frame
- Force density method
- sensitivity analysis
- optimization under uncertainty
date: "2021-08-30T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Optimal result of bridge-like structure
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
  Geometry and topology optimization of truss-like structures is one of the standard topics in structural optimization, and has received considerable attention in the past[1][2]. Generally, optimization of truss-like structures can be classified into three categories; namely, sizing, geometry (or shape) and topology optimization. Among them, sizing optimization, which aims at finding the optimal cross-sectional properties of members, is commonly included in geometry and topology optimization, and the change of structural topology can be achieved in the standard framework of sizing optimization problem. <br/>
  <figure class="half" style="display:flex; align-items: flex-end">
    <img src="ShapeTopo-2.png" style ="width: 70%; height: 70%"> 
  </figure>
  <DIV align="CENTER">
    <b>FIG.1:</b> Initial structure of numerical example
  </DIV>
  <br/>
  When geometry optimization is involved, one of the main challenges is the existence of melting nodes, or coalescent nodes, resulting in extremely short member in the structure and making the stiffness matrix singular[3]. In order to alleviate this diffculty, the force density method (FDM) is introduced for shape optimization which indirectly controls the member length[4]. A numerical example with initial structure shown in Fig.1 is investigated the effectiveness of the proposed method, and the optimization procedure shown in Fig.2 shows that a reasonble optimal result can be obtained by introducing FDM for determining the structural shape, where the red and blue lines indicate the positive and negative force density values, respectively.
  
  <figure class="half" style="display:flex; align-items: flex-end">
    <img src="ShapeTopo-1.jpg" style ="width: 90%; height: 90%"> 
  </figure>
  <DIV align="CENTER">
    <b>FIG.2:</b> Intermediate solutions of numerical example
  </DIV> 
  <br/>
  Moreover, many researches have been proposed to consider uncertainty in structural optimization, such as robust optimization[5], reliability-based optimization[6] and the worst-case design[7], and I am also working on this research topic right now [8][9]. However, incorporating uncertainty into structural optimization is not a trival task expecially the diffculties in efficiency, accuracy and convergence when applied to large-scale problem, I would like to dig more in this research direction.<br/>
  <br/>
  Reference<br/>
  [1] <a href="https://www.runoob.com/" target="_blank" rel="noopener noreferrer">Ohsaki M (2010) Optimization of finite dimensional structures. CRC Press, Boca Raton</a><br/>
  [2] Lewiński T, Sokół T, Graczykowski C (2019) Michell structures. Springer, Berlin
  [3] <a href="https://www.springer.com/gp/book/9783319951799" target="_blank" rel="noopener noreferrer">Achtziger W (2007) On simultaneous optimization of truss geom- etry and topology. Struct Multidiscip Optim 33:285–304.</a><br/>
  [4] <a href="https://link.springer.com/article/10.1007/s00366-019-00923-w" target="_blank" rel="noopener noreferrer">Shen W, Ohsaki M (2021) Geometry and topology optimization of plane frames for compliance minimization using force density method for geometry model. Eng Comput 37:2029–2046.</a><br/>
  [5] <a href="https://onlinelibrary.wiley.com/doi/abs/10.1002/nme.2871" target="_blank" rel="noopener noreferrer">Kanno Y, Xu G (2010) A mixed integer programming for robust truss topology optimization with stress constraints. Int J Numer Methods Eng 83:1675-1699.</a><br/>
  [6] <a href="https://link.springer.com/article/10.1007%2Fs00158-006-0039-5" target="_blank" rel="noopener noreferrer">Mogami K, Nishiwaki S, Izui K, Yoshimura M, Kogiso N (2006) Reliability-based structural optimization of frame structures for multiple failure criteria using topology optimization techniques. Struct Multidiscip Optim 32(4):299-311.</a><br/> 
  [7] <a href="https://www.sciencedirect.com/science/article/abs/pii/S0093641318305986?via%3Dihub" target="_blank" rel="noopener noreferrer">Ohsaki M, Yamakawa M, Fan W, Li Z (2019) An order statistics approach to multiobjective structural optimization considering robustness and confidence of responses. Mech Res Commun 97:33-38.</a><br/> 
  [8] <a href="https://link.springer.com/article/10.1007/s00158-020-02663-8" target="_blank" rel="noopener noreferrer">Shen W, Ohsaki M, Yamakawa M (2020) Multiobjective robust shape and topology optimization of plane frames using order statistics. Struct Multidiscip Optim 75–94.</a><br/> 
  [9] <a href="https://onlinelibrary.wiley.com/doi/full/10.1002/nme.6676" target="_blank" rel="noopener noreferrer">Shen W, Ohsaki M, Yamakawa M (2021) Robust geometry and topology optimization of plane frames using order statistics and force density method with global stability constraint. Int J Numer Methods Eng 122:3653–3677.</a><br/>  


</DIV>  



