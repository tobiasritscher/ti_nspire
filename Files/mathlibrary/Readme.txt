Help:

-In AAFetch, formulas are called up using the syntax fetch("cone").
The program will then return all formulas up to the Calculus III level involving cones:
volume, surface area, and the quadric surface equation.

-The initial output will be TI-84 looking (e.g. A=p*r^2*h), but it will turn into
nSpire format when you highlight your selected equation, then copy and paste it.
Entering A=p*r^2*h|r=5_cm and h=3_cm is often the easiest way to evaluate.

-By default, the syntax is AAfetch\fetch("cone"). To be able to use the shorter syntax,
type into the scratchpad or your working document
Define fetch(keyword)=Prgm:aafetch/fetch(keyword):EndPrgm.

-Some geometry entries such as fetch("corresponding angles") make images appear on a page that a Lua script. This script can be copied and pasted into other documents by copying its page.

-You can browse all available entries by typing in any of the following into fetch(""):
algebra, geometry, trigonometry, Calculus I, Calculus II, Calculus III, statistics,
linear algebra, differential equations, physics (introductory level).

But if you remember any specific term from these courses, such as "disc method" or "flux integral", there will probably be an entry for it.
Ignore the Programmingtools document, it's just there for a few programming subroutines.

-AAfetch is the main document, except statistics programs are stored under AAStatistics to make them easier to pick out. Ignore the Programmingtools document, but have it in the library. It's leftover from when I once used it for subroutines in my programs.

-Pre-calculus programs:
1) arctrig("arctan(tan(22))")
Inverse trig functions can have two answers, but the calculator uses a definition where the
range is restricted to return one answer and make them one-to-one with trig functions.
This program returns both answers. Works with both radian and degrees mode.
fetch("atan2") returns a piecewise function atan2(y,x) that matches y and x with a specific angle.
fetch("asin2") returns a piecewise function asin2(y,r,sign(x)) that matches y, r, and the sign of x (-1 or 1) with a specific angle.

programs showing steps: 2) completesquwork(x^2+y^2+2x-6y+6,{y,x})
Shows steps to completing the square for up to 3 variables.

Calculus I programs:

1) describefunc() executes the First Derivative Test, Second Derivative Test, and Concavity Test. It finds minima, maxima, intervals on which the function is increasing, decreasing, or constant, and intervals on which the function is concave up, concave down, or linear. It also says if the function is even or odd if it is either.

2) implicitdiff(x*y^2+z,{x,y,z}) Implcitly differentiates and returns df/dx in terms of x,y,z and dy/dx and dz/dx.

programs showing steps:

1) chainrule({u[1]^3,sin(u[2]),4x},x)
Shows the chain rule for sin(4t)^3 as a list of factors, unsimplified. Really only useful for functions where the list would be really long.

2) productquorule(f(x),x) Shows the unsimplified version of the derivative of a function using the product rule or quotient rule (multiple times).

3) usub(function,u(var),var) Shows steps for u-substitution and returns an answer.

4) If you copy and paste a single definite integral into fetch(""), it will show the three "integrate, find f(b) and f(a), find f(b)-f(a)" steps.

Calculus II programs:

programs showing steps:

1) integbyparts(fvar,u,dv,var) Shows steps to integration by parts, if u is a polynomial.
2) trigsub(fx,ux,ax) Shows steps to trigonometric substitution.

Calculus III programs:

1) crossPsteps(column_vector1,column_vector2) Shows steps to evaluating a cross product via the box method and returns a result.

2) grad(f,vars,pt,coord_sys) Enter vars and pt as a vector column, and enter both as [x y z] to not evaluate at a point. Enter coord_sys as "rectangular" or "polar" or "cylindrical", "spherical", or a vector column of Cartesian-to-other expressions.
3) Dv(f,vec,vars,pt,coord_sys) Finds the directional derivative.
4) curl(vector_field,vars,pt,coord_sys)
5) div(vector_field,vars,pt,coord_sys)
6) laplacian(f,vars,pt,coord_sys)

7) totaldiff(f(x,y,z),[[x][y][z]],[[x0][y0][z0]],[[dx][dy][dz]]) Finds the total differential of a function of n variables.

8) jacobian([x(q)],[q]), e.g. jacobian([[r*cos(theta)][r*sin(theta)]],[[r][theta]]) 

9) hessian(f(x,y,z),[[x][y][z]],[[x0][y0][z0]]) Returns the Hessian matrix. See fetch("Hessian") for more information.

10) metric_factors([[r*cos(?)][r*sin(?)]],[[r][?]]) see: fetch("metric factor"), fetch("curvilinear")

11) If you copy and paste a double or triple definite integral into fetch(""), it will show the six or nine "integrate, find f(b) and f(a), find f(b)-f(a)" steps for the inner, middle, and outer integrands.

-fetch("center of mass") brings up a list of functions for calculating center of mass or moment of intertia over a planar region, volume, line integral, or surface area.

Statistics programs:
1) randomsample({list}) returns only statistics relevant to continuous data, as opposed to nSpire's default version, which misleadingly returns a population variance using a formula for discrete data.
2) func_stddev(f(x,y,z),[[x][y][z]],[[x_0][y_0][z_0]],[[dx][dy][dz]]) Finds the standard deviation of a function of n variables, given the error of the arguments in the form of vector columns of their standard deviations. see: fetch("variance of a function")

These are stand-alone programs for determining a few metrics when f(x) is already known. If you reference these programs in an nSpire spreadsheet, you can use these with curve fitting via sliders on nSpire's graph screen and watch the metrics change as you fit f(x) to the scatterplot:
4) R_sq(y,y_estimate) 
4) R_a_sq(y,y_estimate) 
6) RMS(y,y_estimate)
7) MAE(y,y_estimate)

8) multiregression(basis,matrix) See fetch("multiple linear regression") for a fuller explanation.
9) partitions(r_list) Finds the number of possible ways to partition a set of n elements into sets of r_i elements.
10) hypergeomPdf(n,r,N,x)
11) hypergeomCdf(n,r,N,x_1,x_2)

These are intended to remove the need to create a table:
12) invDiscretePdf(P,f(x),xdomain,"left")  Find x_0 closest to P on the side of the distribution left or right of the peak.
13) invDiscreteCdf(P,f(x),xdomain,">=") Returns the x_0 such that P_table is barely = P; lower-tailed like invNorm.
14) invBinomPdf(P,n,p)
15) invBinomCdf(P,n,p,">=")
16) invPoissPdf(P,n,?)
17) invPoissCdf(P,n,?,">=") 
18) invHypergeomPdf(P,n,r,N)
19) invHypergeomCdf(P,n,r,N,">=")

Linear Algebra programs:

1) kernelbasis(A) Returns the basis of the nullspace/kernel of A.

2) kernelvectors(A) Returns a vector column using a set of parameters {k_i}.

3) generalsolution(A,b) Displays the nullspace basis and the particular solution of a system, then returns the general solution as a single column vector using parmeters {k_i}.

4) wronskian({f_list},var)

5) vectspacetest(u,v,w). After defining scale(), add(), neg(), and zero(), if you enter a generic version of vectors u, v, and w in any format nSpire can handle, such as a column [u1, u2, u3], this will automatically test your definitions against the 10 axioms that define a vector space. Type fetch("vector space") for more background.

6) innerPtest(u,v,w,zero,{other_vars}) After defining an inner product using innerP(u,v,[any other variables]), such as ? u*v dx over [a,b], this will test your definition to see if it fits against the axioms that define an inner product space. Type fetch("inner product space") for more background. 

7) gramschmidt(basis) Returns an orthonormal basis. Input can be a matrix, a function, or a list of functions. It will use your defined inner product, and default to the dot product if none is defined. qrdecomp(basis) will also return R.

8) There are five programs that deal with matrix sequences, recursive matrix sequences, matrix series, matrix left product series, and matrix right product series.

Sequence: matseq("matrix",var,low,high,step)
Summation: matsum("matrix",var,low,high)
Left product: matleftprod("matrix",var,low,high)
Right product: matrightprod("matrix",var,low,high)
Recursive sequence: Use the following format:
matrecursiveseq("[[.8,.3][.2,.7]]*term(n-1)",[["m=2",0]["n=1",1]],#terms)

9) vandermonde(x_column,y_column) Returns a polynomial. see: fetch("Vandermonde")

10) rank(A) Returns the rank of a matrix.

11) overdetermined(A_coef) Given the coefficient matrix of a system that will not be consistent for all values of b, this returns a vector column using parameters {k_i} of the vectors for which the system will be consistent. see: fetch("Rouch?'s Theorem"), fetch("overdetermined")

12) diagonalize(A) This will detect if A is unitarily diagonalizable, orthogonally diagonalizable, or diagonalizable at all, and return why not if it can't. It will then return the eigenbasis P or orthonormal eigenbasis P that diagonalizes A, as well as the diagonal matrix.

13) principleaxes(v) Given a column of the six coefficients of a conic or nine coefficients of a quadric, this will return a conic or quadric rotated such that the conic or quadric is centered on coordinate axes. see: fetch("Principle Axes Theorem")