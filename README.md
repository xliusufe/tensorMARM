# tensorMARM
 Multivariate additive regression for multi-view data via tensor estimation.

    For a multivariate additive model (MARM), the B-spline base functions are applied to approximate the additive components. We treat the coefficients as multiple third-order tensors or even a fourth-order tensor for some specific structure (called structural MARM). With the tensor low-rankness, the Tucker decomposition and group sparse penalty (lasso, mcp or scad) reduce the number of parameters. A blockwise coordinate descent algorithm is used to estimate the core tensors and factor matrices, and feature selection.
# Installation

	#install Rtools 3.5 (http://cran.r-project.org/bin/windows/Rtools)
	#install.packages("devtools")
	#install.packages("Rcpp")
	library(devtools)
	install_github("xliusufe/tensorMARM")

# Usage

   - [x] [tensorMARM-manual](https://github.com/xliusufe/tensorMARM/blob/master/inst/tensorMARM-manual.pdf) ------------ Details of the usage of the package.
# Examples

	library(tensorMARM)
	# Example 1
	# The usage of function "immam3.dr"
	n <- 200
	q <- 5
	p <- 100
	s <- 3
	ng <- 4
	group <- rep(1:ng,each=p/ng)
	mydata <- immam3.sim.fbs(n,q,p,s,group)
	fit <- with(mydata, immam3.dr(Y,X,group,K,r1_index,r2_index,r3_index,D0=D0,nlam=5))

	# Example 2
	# The usage of function "immam4.dr"
	n <- 200
	q <- 5
	p <- 100
	s <- 3
	ng <- 4
	group <- rep(1:ng,each=p/ng)
	mydata <- immam4.sim.fbs(n,q,p,s,group)
	fit <- with(mydata, immam4.dr(Y,X,group,K,r1_index,r2_index,r3_index,r4_index,D0=D0,nlam=5))

	# Example 3
	# The usage of function "immam3"
	n <- 200
	q <- 5
	p <- 100
	s <- 3
	ng <- 4
	group <- rep(1:ng,each=p/ng)
	mydata <- immam3.sim.fbs(n,q,p,s,group,isfixedR=1)
	fit <- with(mydata, immam3(Y,X,group,K,r10,r20,r30,D0=D0,nlam=5))

	# Example 4
	# The usage of function "immam4"
	n <- 200
	q <- 5
	p <- 100
	s <- 3
	ng <- 4
	group <- rep(1:ng,each=p/ng)
	mydata <- immam4.sim.fbs(n,q,p,s,group,isfixedR=1)
	fit <- with(mydata, immam4(Y,X,group,K,r10,r20,r30,r40,D0=D0,nlam=5))


 # References
Multivariate additive regression for multi-view data via tensor estimation. Manuscript.

# Development
The R-package is developed by Xu Liu (liu.xu@sufe.edu.cn) and Yiming Liu.
