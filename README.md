# distortionAnalysis

by Manuel Claeys Boùùaert

## What it does

This code was built to analyse distortion in old maps.

Old, historical maps can be inaccurate for many reasons (primitive techniques, surveying errors, mixed inputs, conservation, etc). 
A distortion represents a loss in geographic information, but, by its specific origin, yields new historical information. 
Hence the study of distortions in old maps.

This code takes as input a set of common ground control points, identified both on the old map and on a modern reference map.
Based on these points, an interpolation is constructed between both maps. 
From this interpolation, the distortions (such as stretching or shearing) are computed using common distortion visualisation techniques, including displacement vectors, distortion grids, Tissot indicatrices and a new technique called **Differential Distortion Analysis**.

The output is a set of `.WKT` and `.csv` files with the corresponding distortion features and values.

Bonus: this code can also be used in similar settings where 2D objects are warped, such as abstracted maps (e.g. transit maps), mental maps, maps of deformed terrain (glaciers, tectonics), etc. Feel inspired!

## How to use it

The `.m` code is fully Matlab and Octave compatible.

In order to build the interpolation, you should have access to either the Octave Splines Package or Matlab CurveFitting Toolbox.
(The Octave Splines Package can be installed using `pkg install -forge -global -auto splines`)

The `example.m` file demonstrates how to load data, set optional parameters and call the main function `distortionAnalysis.m`.

For further usage, visualise the output documents in a (web-)GIS application. Interpolate the point-wise results in the `.csv` files for optimal visualisations.

## How to cite it

### Code

Manuel Claeys Boùùaert wrote this code in 2015 for a project analysing distortion in the 1777 '[Carte de Cabinet](http://belgica.kbr.be/nl/coll/cp/cpFerraris_nl.html)' of the Austrian Netherlands by count de Ferraris.

If you want use this code for scientific work, **please refer to the following publication**:

*Claeys Boùùaert, M., De Baets, B., Vervust, S., Neutens, T., De Maeyer, P., Van De Weghe N., 2015. Computation and visualisation of the accuracy of old maps using differential distortion analysis. International Journal of Geographical Information Science.*  
<http://dx.doi.org/10.1080/13658816.2015.1127377>

### Sample data

The sample data map is courtesy of swisstopo (map collection, LT K BL 1798).   
The sample data ground control points are courtesy of Martin Rickenbacher (Bern).

This sample data is similar to the one used in the [MapAnalyst](<http://www.mapanalyst.org>) software by Bernhard Jenny, which has inspired us during our work.

### Octave Splines package

The [Splines Package](http://octave.sourceforge.net/splines) for GNU Octave is written by Nir Y. Krakauer and others. It features the commands used in this code since version 1.2.9.