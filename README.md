# GFDL Ocean Model Grid Generator
A collection of tools for creating finite element spherical tripolar grids for GFDL's MOM based ocean models.

Required python packages:
- numpypi : python -m pip install git+https://github.com/underwoo/numpypi@pip.installable
 
To test this module quickly try
- cd extras ; make quick

Examples:
- To build a grid with a 1/4 degree nominal resolution that omits the southern cap, ensures an even number of latitude points, and creates a bipolar grid north of 65°N. The grid transitions to a Mercator projection from 75°S to 65°N, matching the grid spacing to that of the Southern Ocean. Additionally, the grid is shifted to align the equator with a u-point:
 
ocean_grid_generator.py -r 4 --no_south_cap --ensure_nj_even --bipolar_lower_lat 65 --mercator_lower_lat -75 --mercator_upper_lat 65 --match_dy so --shift_equator_to_u_point --south_ocean_lower_lat -81 


[Technical guide](https://github.com/nikizadehgfdl/grid_generation/blob/dev/ocean_grid_generator_guide.pdf)

[![Build Status](https://travis-ci.org/nikizadehgfdl/ocean_model_grid_generator.svg?branch=dev)](https://travis-ci.org/nikizadehgfdl/ocean_model_grid_generator)

