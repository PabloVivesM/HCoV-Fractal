# HCoV-Fractal
Code for generating (filled) Julia Sets and the Mandelbrot Set

## Julia Set
The code for the Julia Set is based on the backwards iteration method outlined in the textbook "Encounters with Chaos and Fractals" by Denny Gulick. Given a rectangular region in `C`, we make an NxN grid of points. We then proceed to apply the inverse to this grid m times. The inverse of `f(c,x)=x^2+c` has two branches (the positive or negative square root) so a each step we pick a random 'direction', plus or minus. In this way, the Julia Set is generated.

## Escape Time Approximation
### Mandelbrot Set
It can be shown that all points in the Mandelbrot set are at a distance of less than 2 from the origin. Using this, we say that a point is in the Mandlebrot Set if `|f^k(0)| < 2` for all natural numbers k. In practise, we must place an upper limit on k, so when computing we say that a point z is in the Mandelbrot Set if for `|f^k(z, 0)| < 2` for all `k < upper_limit`. If we keep track of the value k* at which the limit is surpassed (otherwise `k* = upper_limit`), we can plot the number and colour the set, creating the patterns seen online.

### Filled Julia Set
Similarly for the Filled Julia Set, `K_c`, all points are at a distance less than `1 + |c|` from the origin. Again, a point z will be in K_c if `|f^k(c, z)| < 1 + |c|` for all `k < upper_limit`. Finally, colouring based on the value of k* produces the famous Julia Set images.


## Example commands
### Generating
* `FilledJulia((-1,1), (-1,1), -0.157 + 1.031*1j, 1000, 256, 'ex0')`
* `FilledJulia((-1.5, 1.5), (-1.5, 1.5), -0.4 -0.59*1j, 1000, 256, 'ex1')`
* `FilledJulia((-0.05, 0.75), (-0.05, 0.75), -0.4 -0.59*1j, 1000, 256, 'ex2')`
* `FilledJulia((-1.5, 1.5), (-1.5, 1.5), -0.8 + 0.156*1j, 2000, 256, 'valley_julia')`
* `Mandelbrot((-0.82,-0.72), (0.1, 0.2), 1000, 256, 'valley')`
* `Mandelbrot((-2,0.6), (-1.3, 1.3), 2000, 256, 'basicMandl')`
* `Mandelbrot((-0.174,-0.144), (-1.0495, -1.0195), 2000, 256, 'babyMandl')`
* `Mandelbrot((-0.27,-0.02), (-1.1, -0.85), 2000, 256, 'littleMandl')`

### Displaying (must have previously generated)
* `display('ex1', blue_base, 90, ['#00AC09', '#FFD928'], '#000000', True)`
* `display('ex2', blue_base, 90, ['#00AC09', '#FFD928'], '#000000', True)`
* `display('valley', purpl_base, 200, ['#E40000', '#74E400', '#0060E4'], '#000000', True)`
* `display('basicMandl', purpl_base, 200, ['#E40000', '#74E400', '#0060E4'], '#000000', True)`
* `display('babyMandl', red_base, 120, ['#FF3A3A', '#3D3AFF', '#DC47FF'], '#000000', True)`
* `display('littleMandl', purpl_base, 130, ['#FF3A3A', '#3D3AFF', '#DC47FF'], '#000000', True)`
* `display('valley_julia', blue_base, 110, ['#9844ff', '#5200b7'], '#000000', True)`

### Julia Set
* `JuliaOutline((-1, 1), (-1, 1), c=-0.123+1j*0.745, points=50000, point_size=1)`
* `JuliaOutline((-1, 1), (-1, 1), c=1j, points=50000, point_size=0.5)`
* `JuliaOutline((-1, 1), (-1, 1), c=0.32+0.043*1j, points=50000, point_size=0.5)`
* `JuliaOutline((-1, 1), (-1, 1), c=0.355 + 0.355*1j, points=50000, point_size=1)`
* `JuliaOutline((-1, 1), (-1, 1), c=-1.75, points=50000, point_size=1)`
* `JuliaOutline((-1, 1), (-1, 1), c=0, points=50000, point_size=1)`
