---
title: Structural reliability analysis
summary: In practical uncertainty is almost inevitable in structural stiffness and external load, and balancing the efficiency and accuracy of reliability analysis method is still challenging and attractive.
tags:
- component and system reliability analysis
- dimension-reduction method
- reliability analysis method
date: "2021-08-30T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Reliability analysis of cantilever beam
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
  I began to learn and study reliability analysis when I was a master student. The reliability analysis of an engineering system or component is typically based on a model that describes structural response $ Y $ as a function of basic random $ \boldsymbol{X} $ variables, which can be given mathematically
  
  \begin{equation} \small  
  Y = f \left ( \boldsymbol{X} \right )
  \tag{1}
  \end{equation}
  
  The probability of failure $ P_{f} $ is defined as the probability of structural response being in a domain of unacceptable operation, such as response exceeding a critical threshold, $ y_{c} $, and it is typically defined in terms of a limit state function

  \begin{equation} \small
  g \left ( \boldsymbol{X} \right ) = y_{c} - f \left ( \boldsymbol{X} \right ) \quad
  {\rm such\ that}\ P_{f} = {\rm Pr}\left [ g \left ( \boldsymbol{X} \right ) \leq 0 \right ]
  \tag{2}
  \end{equation}
  
  There are a number of reliability analysis method, like Monte Carlo simulation (MCS)[1],first-order reliability method (FORM)[2],second-order reliability method[3] and the moment methods[4]. One of the main challenges is to balance the accuracy and efficiency of the reliability analysis, that is
  <ul>
    <li> minimize the function evaluations </li>
    <li> find the most appropriate probability distribution or explicit approximation of the implicit limt state function </li>
  </ul>
  To achieve this goal,a polynomial response surface method with adapative bivariate dimensional reduction method is proposed [5] in which a criteria is introduced to eliminate the unnecessary quadratic term in response surface function [6]. In this way the efficiency could be enhanced without great loss of accuracy. An numerical example of cantilever beam, which is shown in Fig.1, is used to investigated the effectiveness of proposed method. The limit state function is defined as the displacement of point B is equal to 15mm in vertical direction and the limit state function is then formulated  as [7]
  \begin{equation} \small
  g \left (q,F_1,F_2,E \right )=15 - \frac{qL^4}{8EI}-\frac{5 F_1 L^3}{48EI} - \frac{F_2 L^3}{3EI}
  \tag{3}
  \end{equation}

  <figure class="half" style="display:flex; align-items: flex-end">
    <img src="reliability-2.jpg" style ="width: 50%; height: 50%"> 
  </figure>
  <DIV align="CENTER">
    <b>FIG.1:</b> The model of numerical example
  </DIV>
  <br/>
  and the results obtained by MCS, proposed method, RSM with only quadratic term (QP) and complete quadratic term (CQP) are shown in Table 1,where $ \beta,\ k_final,\ and\ N  $ is the Hasofer-Lind Rackwitz-Fiessler(HL-RF) reliability index, the number of iterations and function evaluations. It can be observed that the proposed method is able to obtain accurate result with less function evaluations
</DIV> 
<br/>

<DIV align="CENTER">
    <b>Table 1</b> Results summary of numerical example
</DIV>

  <table border="1" cellspacing="0" frame=hsides rules = all>
    <tr>
      <td align="center" width = "200" > Method </td>
      <td align="center" width = "200" > $ k_{final} $ </td>
      <td align="center" width = "200" > $ N $ </td>
      <td align="center" width = "200" > $ \beta $ </td>
      <td align="center" width = "200" > Error(%) </td>
    </tr>
    <tr>
      <td align="center" width = "200" > MCS </td>
      <td align="center" width = "200" > -- </td>
      <td align="center" width = "200" > $ 10^7 $ </td>
      <td align="center" width = "200" > 2.725 </td>
      <td align="center" width = "200" > -- </td>
    </tr>
    <tr>
      <td align="center"> RSM with QP </td>
      <td align="center"> 3 </td>
      <td align="center"> 23 </td>
      <td align="center"> 2.710 </td>
      <td align="center"> 0.6 </td>
    </tr>
    <tr>
      <td align="center"> RSM with CQP </td>
      <td align="center"> 3 </td>
      <td align="center"> 39 </td>
      <td align="center"> 2.619 </td>
      <td align="center"> 3.9 </td>
    </tr>
    <tr>
      <td align="center"> proposed method </td>
      <td align="center"> 3 </td>
      <td align="center"> 25 </td>
      <td align="center"> 2.710 </td>
      <td align="center"> 0.6 </td>
    </tr>
  </table>


<font size="4" font face = "Times New Roman">
<DIV align="justify">

  However, the method only consider component reliability analysis within linear elasticity case. In the future I would like to dig more about structural reliability analysis in system or dynamic case.

  <br/>
  Reference <br/>
  [1] <a href="https://www.wiley.com/en-us/Simulation+and+the+Monte+Carlo+Method%2C+3rd+Edition-p-9781118632161" target="_blank" rel="noopener noreferrer">Rubinstein RY (1981) Simulation and the Monte Carlo method.Wiley,New York </a><br/>
  [2] <a href="https://www.sciencedirect.com/science/article/pii/0167473082900248" target="_blank" rel="noopener noreferrer">Hohenbichler M, Rackwitz R (1982) First-order concepts in system reliability. Structural safety 1(3): 177-188. </a><br/>
  [3] <a href="https://ascelibrary.org/doi/abs/10.1061/(ASCE)0733-9399(1984)110:3(357)" target="_blank" rel="noopener noreferrer">Breitung K (1984) Asymptotic approximations for multinormal integrals. Journal of Engineering Mechanics 110(3): 357-366.</a><br/>
  [4] <a href="https://link.springer.com/article/10.1007%2Fs00158-011-0656-5" target="_blank" rel="noopener noreferrer">Xi Z, Hu C, Youn BD (2012) A comparative study of probability estimation methods for reliability analysis. Struct Multidiscip Optim 45:33???52.</a><br/> 
  [5] <a href="https://www.emerald.com/insight/content/doi/10.1108/EC-06-2020-0343/full/html?utm_source=rss&utm_medium=feed&utm_campaign=rss_journalLatest" target="_blank" rel="noopener noreferrer">Fan W, Shen W, Zhang Q, et al. A new response surface method based on the adaptive bivariate cut-HDMR. Engineering Computations.</a><br/> 
  [6] <a href="https://www.sciencedirect.com/science/article/pii/S0266892015300527" target="_blank" rel="noopener noreferrer">Fan W, Wei J, Ang AHS, Li Z (2016) Adaptive estimation of statistical moments of the responses of random systems. Probabilistic Eng Mech 43:50???67.</a><br/> 
  [7] <a href="https://www.sciencedirect.com/science/article/pii/S0045782508003617" target="_blank" rel="noopener noreferrer">Chowdhury R, Rao BN (2009) Hybrid High Dimensional Model Representation for reliability analysis. Computer Methods in Applied Mechanics & Engineering 198(5 :753-765.</a><br/> 

</DIV> 



