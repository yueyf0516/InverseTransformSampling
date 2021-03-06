InverseTransformSampling
========================

Matlab implementation of inverse transform sampling in 1D and 2D.  This requires version 5.0 (or above) of chebfun2:

		http://www.chebfun.org/download/
		
		
========================


1D Usage

	sample(pdf, [a b], N);
	
2D Usage

	sample(pdf, [a b], [c d], N);	
	
	
========================
	
		
1D Examples

	X = sample(@(x) exp(-x.^2), [-10 10], 100);
	X = sample(@(x) exp(-x.^2/2).*(1 + (sin(3*x)).^2).*(1 + (cos(5*x).^2)), [-8 8], 100);
	X = sample(@(x) exp(-4.*x.^2).*(9+72.*x.^2 - 192.*x.^4 + 512.*x.^6), [-4 4], 100);	
	X = sample(@(x)  2 + cos(100.*x), [-1 1], 100);		
	X = sample(@(x)  sech(200.*x), [-1 1], 100);			
	
	
2D Examples

	[X Y] = sample(@(x,y) exp(-x.^4/2 - y.^4/2).*(x-y).^2, [-7 7], [-7 7], 100);
	[X Y] = sample(@(x,y) exp(-x.^2-2*y.^2).*sech(10.*x.*y), [-5 5], [-4 4], 100);
	[X Y] = sample(@(x,y) exp(-x.^2-2*y.^2).*(x-y).^2.*sech(10.*x.*y), [-3 3], [-3 3], 100);	
