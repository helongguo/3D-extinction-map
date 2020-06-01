# Southernsky-3D-extinction-map
Description
Based on the multi-band photometry of SkyMapper Southern Survey, the Two Micron All Sky Survey and the Wide-Field Infrared Survey Explorer Survey, we have estimated values of the r-band extinction for∼ 19 million stars with the spectral energy distribution (SED) analysis. 

The best fit stellar parameters for over 17 million stars, inferred by Guo et al. (2019) is publicly available online：

http://paperdata.china-vo.org/guo/dust/SkyMapper_stellar_Ar.fits

The four parameters we infer are:

Coordinate location (“L” and “B”)
Distance (“dis”)
Extinction in the r band (“Ar ”)
The maximum-likelihood (“ χ2 ”)

Reddening is given in an arbitrary unit, which can be converted to magnitudes of extinction in the SMSS, Gaia, WISE and 2MASS passbands by multiplying by the following coefficients: 

g:    3.407

r:    2.685

i；    2.03

J：    0.82

H:    0.52

Ks:   0.35

W1:   0.21

G_BP: 3.24

G_RP: 1.91

A three-dimensional map of dust reddening, covers the SkyMapper Southern Survey (SMSS) area of ∼ 14,000 deg2. We use the multi-band photometry of SMSS, 2MASS and WISE and the distances calculated from the Gaia DR2 parallaxes, to infer distances and reddenings to ~17 million stars. These stars trace the reddening along different lines of sight, allowing us to build up a map of reddening in 3D. The southern sky 3D extinction map is publicly available online：

http://paperdata.china-vo.org/guo/dust/SkyMapperAr.fits

For the parameter of  “Ar ” in the dataset, the distance is from 0 to 6 kpc with a bin size of 0.2 kpc.


we also obtain a 3D extinction map that covers the entire sky by combining the maps presented in the current work and those published by Chen et al. (2019) and Green et al. (2018).

The entire sky 3D extinction map is publicly available online：

http://paperdata.china-vo.org/guo/dust/allskymap_EBV.fits

For the parameter of reddening “EBV” in the dataset, the distance is from 0 to 6 kpc with a bin size of 0.2 kpc.

In the work of Guo et al.(2020), we also get a library of reference stellar loci. We have gave the description in the file of "Addition dataset"

Here, we briefly introduce how to use our code to get the extinction value of a place.
For example, if you want to get the extinction of a star at (L, B, DIS). After running our code， when you input southernskydust_map(L ,B ,DIS ), you will get a value in E(B - V) inferred from our southern sky 3D extinction map.

southernskydust_map( 277.23 ,-8.64 ,4.9 )

input:l,b,d,unit=[deg, kpc],d<=6.0,fram=galactic,output:E(B-V) 

array([[0.16344043]])

when you input allskydust_map(L ,B ,DIS ), you will get a value in E(B - V) inferred from our all sky 3D extinction map.

allskydust_map(200.23   , 18.64   , 1.9 )

input:l,b,d,unit=[deg,kpc],d<=6.0,fram=galactic,output:E(B-V)

array([[0.03141569]])

Please note tha， in our code, the location must be in galactic cooddinate (L,B) and in the unit of deg and the distance must be in unit of kpc. If you give a diatance larger than 6.0 kpc, you will get a value of nan.



