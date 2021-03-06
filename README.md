# ZOGY
a Python implementation of proper image subtraction (Zackay, Ofek &amp; Gal-Yam 2016, ApJ, 830, 27)

Written by Paul Vreeswijk with vital input from Barak Zackay and Eran Ofek. Adapted by Kerry Paterson for integration into pipeline for MeerLICHT.

This module accepts a new and a reference fits image, finds their WCS solution using Astrometry.net, runs SExtractor (inside Astrometry.net), PSFex to extract the PSF from the images, and performs optimal image subtraction following Zackay et al. (2016) to produce the subtracted image (D), the significance image (S), the corrected significance image (Scorr), and PSF photometry image (Fpsf - alpha in the paper) and associated error image (Fpsferr).

It makes grateful use of the following programs that first need to be installed:

 - Astrometry.net (in particular "solve-field" and index files): http://astrometry.net 
 - SExtractor: http://www.astromatic.net/software/sextractor
 - SWarp: http://www.astromatic.net/software/swarp
 - PSFex: http://www.astromatic.net/software/psfex
 - ds9
 - sip_to_pv module from David Shupe: https://github.com/stargaser/sip_tpv/blob/master/sip_to_pv.py
 - pyfftw to speed up the many FFTs performed
 - the other modules imported at the top (e.g. astropy, matplotlib, etc.)
 
Warning: this module is still being developed and has so far only been tested on a couple of KMTNet images. It is designed specifically to be included in the MeerLICHT and BlackGEM pipelines. However, the hope is to make it more general in the near future so any two images can be supplied to perform optimal subtraction on.
