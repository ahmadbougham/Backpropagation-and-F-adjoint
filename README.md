
# Backpropagation-and-F-adjoint
The main goal of this project is to implement the well-known backpropagation algorithm in an easy manner based on the idea of the F-adjoint propagation proposed in the following arxiv preprint: "[Backpropagation and F-adjoint. arXiv preprint arXiv:2304.13820.](https://arxiv.org/abs/2304.13820)"

Hereafter, we shall recall the background and notation used in the above reference.
## Background and Notation 
We consider the simple case of a fully-connected deep multi-layer perceptron (MLP) composed of $L$ layers trained in a supervised setting.
we will denote such an architecture by $A[N_0, \cdots, N_\ell,\cdots, N_L]$, where $N_0$ is the size of the input layer, $N_\ell$ is the size of hidden layer $\ell$,
and $N_L$ is the size of the output layer. In particular, we denote $W^{\ell}$ the Weight matrix of the layer ${\ell}$,  $W^{\ell}\in\mathbb{R}^{N_{\ell}\times N_{\ell-1}}$,
 $Y^{\ell}$  Preactivation vector at layer ${\ell}$, $Y^{\ell} = W^{\ell}X^{\ell-1}\in\mathbb{R}^{N_{\ell}}$, $X^{\ell}$  Activition vector at the layer ${\ell}$, $X^{\ell} =\sigma^{\ell}(Y^{\ell})\in\mathbb{R}^{N_{\ell}}$, $\sigma^\ell$  Point-wise activition function of the layer ${\ell}$, $\sigma^\ell :\mathbb{R}^{N_{\ell}}\ni Y^{\ell}\longmapsto\sigma^{\ell}(Y^{\ell})\in\mathbb{R}^{N_{\ell}}$


## The F-propagation and F-adjoint
For the sake of coherency  of presentation we shall recall and revise the  definition of the this notion. 

**Definition of an $F$-propagation** 

Le $X^0\in\mathbb{R}^{N_0}$ be a given data, $\sigma$ be a coordinate-wise map from $\mathbb{R}^{N_\ell}$ into $\mathbb{R}^{N_{\ell+1}}$ and $W^{\ell}\in \mathbb{R}^{{N_{\ell}}\times{N_{\ell-1}}}$ for all ${1\leq \ell\leq L}$. We say that we have a two-step recursive F-propagation   $F$  through the DNN $A[N_0,\cdots, N_L]$ if   one has the following family of vectors
$F(X^0):=[X^{0},Y^{1},X^{1},\cdots,X^{L-1},Y^{L},X^{L}]$ with $Y^\ell=W^{\ell}X^{\ell-1}, \ X^\ell=\sigma(Y^\ell),\ X^\ell\in\mathbb{R}^{N_\ell},\ \ell=1,\cdots, L.$

Before going further, let us point that in the above definition the prefix "F" stands for "Feed-forward".

**Definition of the F-adjoint of an F-propagation**

Let $X^0\in\mathbb{R}^{N_0}$ be a given data and let  $X^0_*\in\mathbb{R}^{N_L}$ be a given vector. We define the $F$-adjoint as the sequence of the following backward steps denoted by $[X_*^L,Y_*^L,\cdots, Y_*^1,X_*^0]$, where $Y^\ell_{*}=X^{\ell}_{*}\odot {\sigma}'(Y^\ell), \ X^{\ell-1}_{*}=(W^\ell)^\top Y^\ell_{*},\ h=L,\cdots, 1.$ 



## References

<div id="refs" class="references">


Backpropagation and F-adjoint. arXiv preprint arXiv:2304.13820.(https://arxiv.org/abs/2304.13820)

</div>

P.S.
Any comments and suggestions are welcome, and readers should feel free to contact me via the following e-mail: ahmadboughamoura@gmail.com
