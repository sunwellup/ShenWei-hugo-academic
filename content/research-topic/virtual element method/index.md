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
<font size="4" font face = "Times New Roman">
<DIV align="justify">
  VEM is a recently proposed numerical discretization technique in Galerkin framework which is inspired by mimic finite difference (MFD) method, and since the date of birth it has been extensively developed and applied to a wide range of engineering problems. The core of the method is to construct a projector which projects the function in local virtual element space (or say, local shape function space) to a polynomial space with prescribed order. In this way VEM avoids the explicit construction of shape function and its integral over the element domain; and thus VEM is able to handle arbitrary polygonal mesh.<br/>
  <br/>
</DIV>   
<DIV align="justify"> 
  In order to give a simple and general illustration of how VEM works, here I take a linear elasticity boundary value problem in 2-dimensional domain $ \boldsymbol\Omega $ as example. The domain is partitioned into arbitrary polygonal meshes <i>$T_h$</i>, and suppose one of the elements is pentagon as shown in Fig. 1.The weak form of the boundary value problem of this pentagon element <i>K</i> is given as
  \begin{equation} \small
  a^K\left ( \boldsymbol{u}^K, \boldsymbol{v}^K \right ) = \int_{\boldsymbol{\Omega}}^K \boldsymbol{\sigma\left ( \boldsymbol{u}^K\right )}:
  \boldsymbol{\epsilon\left ( \boldsymbol{v}\right )} d\boldsymbol{\Omega}^K = f^K \left( \boldsymbol{v}^K \right )=
  \int_{\partial\boldsymbol{\Omega}^K} \boldsymbol{v}^K \cdot \boldsymbol{t} d\partial\boldsymbol{\Omega}^K,\ \forall \boldsymbol{v}^K\in V\left(K\right) \times V\left(K\right)    
  \tag{1}
  \end{equation}
where in Eq.(1) <i>$\boldsymbol\sigma$</i> and <i>$\boldsymbol\epsilon$</i> are the stress and strain tensors, respectively, and $ boldsymbol{v} $ is the test vector-value function which belongs to the local Sobolev space $ V(K)\times V(K) $ defined within the element <i>K</i>; $ \boldsymbol{u} $ is the solution of vector-value function to be found, typically the displacement vector in <i>x</i>- and <i>y</i>-directions; $ \boldsymbol{\Omega}^K $ is the element domain and $ \boldsymbol{\partial\Omega}^K $ is the corresponding Neumann boundary of element <i>K</i>. <br/>
</DIV> 
{{< figure src="VEM-1.png" title="DOFs of second-order VEM" numbered="true" >}} <br/>
</font> 
  
<font size="4" font face = "Times New Roman">
<DIV align="justify">  
 Generally the solution $ boldsymbol{u} $ is approximated by a function in the subspace of $ V_h(K)\times V_h(K) \subseteq V(K)\times V(K) $ called local virtual element space (or say, local shape function space), and the number of basis functions (shape functions) that span  $ V_h(K)\times V_h(K) $ is equal to the number of degrees of freedom (DOFs) of element <i>K</i> defined in the following. Let the element in $ V_h(K)\times V_h(K) $ denote as $ \boldsymbol{v}_h $, the the vector-value function $ boldsymbol{v}_h $ in second-order VEM has the following properties:<br/>
  <ul>
  <li> $ \boldsymbol{v}_h $ is continuous on the boundary of element <i>K</i> </li>
  <li> $ \boldsymbol{v}_h $ is a vector with second-order polynomial components on each edge of element <i>K</i> </li>
  <li> $ \Delta \boldsymbol{v}_h $ is a vector with second-order polynomial components on each edge of element <i>K</i> </li> 
  </ul>  
where $ \Delta $ is the Laplace operator. <b> The corresponding DOFs of element <i>K</i> can be classified into the following three types </b>
  <ol style="list-style-type:lower-roman">
    <li> The values of $ \boldsymbol{v}_h $ at the 5 vertices of element <i>K</i> </li>
    <li> The values of $ \boldsymbol{v}_h $ at the 5 midpoints of 5 edges of element <i>K</i> </li>
    <li> The two moments of $ \boldsymbol{v}_h $ with respect to the constant vectors $ \boldsymbol{p}_1=[1,0]^T $ and $ \boldsymbol{p}_2=[0,1]^T $ in element <i>K</i>, that is </li>
    \begin{equation} \small
    \frac{1}{\lvert \boldsymbol{\Omega}^K \rvert} \int_{\boldsymbol{\Omega}^K} \boldsymbol{v}_h \cdot \boldsymbol{p}_1 d\boldsymbol{\Omega}^K; \quad
    \frac{1}{\lvert \boldsymbol{\Omega}^K \rvert} \int_{\boldsymbol{\Omega}^K} \boldsymbol{v}_h \cdot \boldsymbol{p}_2 d\boldsymbol{\Omega}^K    
    \tag{2}
    \end{equation}
  </ol>
where $ \lvert \boldsymbol{\Omega}^K \rvert $ is the area of element <i>K</i>. Based on the DOFs of types (i)-(iii), the total number of DOFs of element <i>K</i> for the second-order VEM is 5+5+2=12. Therefore, the function $ \boldsymbol{v}_h $ is obtained by a linear combination of the basis functions in $ V_h(K)\times V_h(K) $ as follow
  \begin{equation} \small
  \boldsymbol{v}_h = \sum_{i=1}^{12} {\rm dof}_i\left( \boldsymbol{v}_h \right ) \boldsymbol{\varphi}_i
  \tag{3}
  \end{equation}
where $ dof_i( \boldsymbol{v}_h) $ represents the <i>i</i>th DOF of $ \boldsymbol{v}_h $ as given in types (i)-(iii) above, and $ \boldsymbol{\varphi}_i $ is the <i>i</i>th vector-valued basis function of the local virtual element space $ V_h(K)\times V_h(K) $ of element <i>K</i> with the following two properties
  <ul>
  <li> <b>Property 1</b>: $ \boldsymbol{\varphi}_i(1,2,...,12) $ is a second-order polynomial on the element edge;</li>
  <li> <b>Property 2</b>: $ \boldsymbol{\varphi}_i(1,2,...,12) $ satisfies the Kronecker-delta property, that is, for the <i>j</i>th DOF of element <i>K</i> we have 
    $ {\rm dof}_j\left( \boldsymbol{\varphi}_i \right ) = \delta_{ij},\ i,j=1,2,...,12 $  </li>
 </ul>
  </br>
 </DIV>  
<font size="4" font face = "Times New Roman">
<DIV align="justify">
  Similar to classical Galerkin finite element method (FEM), the entry of local stiffness matrix <i><b>k</b>^K</i> of element <i>K</i> is calculated as 
  \begin{equation} \small
  \left (\boldsymbol{k}^K \right)_{ij} = a^K \left ( \boldsymbol{\varphi}_i, \boldsymbol{\varphi}_j \right )=
  \int_{\boldsymbol{\Omega}^K} \boldsymbol{\sigma}\left ( \boldsymbol{\varphi}_i \right ) : \boldsymbol{\epsilon}\left ( \boldsymbol{\varphi}_j \right ) 
  d\boldsymbol{\Omega}^K, \quad {\rm for}\ i,j=1,2,...,12
  \tag{4}
  \end{equation}
where the subscripts <i>ij</i> indicate the location of entry in <i><b>k</b>^K</i>. <b>Now comes the most important part of VEM: define a projector 
  $ {\rm \Pi}^\nabla: V_h(K)\times V_h(K) \rightarrow  P^2 \times P^2 $ which maps the function $ \boldsymbol{v}_h $ in the space $ V_h(K)\times V_h(K) $
  onto the second-order polynomial space $ P^2 \times P^2 $ satisfying the following orthogonality condition:</b>
  \begin{equation} \small
  a^K \left ( \boldsymbol{p}_\alpha, {\rm \Pi}^\nabla \boldsymbol{v}_h - \boldsymbol{v}_h  \right ) = 0, \quad 
  {\rm for}\ \forall \boldsymbol{p}_{\alpha} \in P_2 \times P_2 {\rm and} \boldsymbol{v}_h \in V_h \times V_h
  \tag{5}
  \end{equation}
where $ \boldsymbol{p}_{\alpha} $ are the polynomial basis functions that span the second-order polynomial space $ P_2 \times P_2 $. Then Eq.(4) is reformulated by using the projector $ \Pi^\nabla $ as 
  \begin{equation} \small
  \left (\boldsymbol{k}^K \right)_{ij} = a^K \left ( \Pi^\nabla\boldsymbol{\varphi}_i + \left ( \boldsymbol{\varphi}_i - \Pi^\nabla\boldsymbol{\varphi}_i   \right ), 
  \Pi^\nabla\boldsymbol{\varphi}_j + \left ( \boldsymbol{\varphi}_j - \Pi^\nabla\boldsymbol{\varphi}_j   \right ) \right )= \\\\\\
  \underbrace{a^K \left ( \Pi^\nabla\boldsymbol{\varphi}_i,\Pi^\nabla\boldsymbol{\varphi}_j \right )}_{\rm consistency} + 
  \underbrace{a^K \left ( \boldsymbol{\varphi}_i - \Pi^\nabla\boldsymbol{\varphi}_i, \boldsymbol{\varphi}_j - \Pi^\nabla\boldsymbol{\varphi}_j \right )}_{\rm stability}
  = \left (\boldsymbol{k}_c^K \right)_{ij} + \left (\boldsymbol{k}_s^K \right)_{ij}  
  \tag{6}
  \end{equation}
where $ \Pi^\nabla \boldsymbol{\varphi}_i = \sum_{\alpha=1}^{12} S_{i,\alpha} \boldsymbol{p}_\alpha,\ \boldsymbol{p}_\alpha \in P^2\times P^2 $ is the image of basis function 
$ \boldsymbol{\varphi}_i $ projected on the second-order polynomial space which is a linear combination of polynomial basis functions 
  $ \boldsymbol{p}_{\alpha} $ with coefficients $ S_{i,/alpha} $, 
  and $ \left ( \boldsymbol{k}^K  \right )_{ij} $ 
  can be thus considered as the sum of consistency term $ \left ( \boldsymbol{k}_c^K  \right )_{ij} $ 
  and stability term $ \left ( \boldsymbol{k}_s^K  \right )_{ij} $ as shown in Eq.(6). <br/>
  <br/>
   Based on the defination of projector $ \Pi^\nabla $ and linearity of the stain tensor, the component-wise consistency term $ \left ( \boldsymbol{k}_c^K \right ) $ can be obtained explicitly as
  \begin{equation} \small
  
  
  \tag{7}
  \end{equation}
</DIV> 
