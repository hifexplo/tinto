# tinto
A benchmark dataset for hyperspectral geoscience.

Please view the benchmark dataset website here: https://hifexplo.github.io/tinto/

## Overview

Deep learning techniques are increasingly used to automatically derive geological maps from digital outcrop models, lessening interpretation time and (ideally) reducing bias. Such techniques are especially needed when hyperspectral images are back-projected to create data-rich ‘hypercloud’ type digital outcrop models.

However, accurate validation of these automated mapping approaches is a significant challenge, due to the subjective nature of geological mapping and difficulty collecting quantitative validation data. This makes validation of different machine learning approaches for geological applications exceedingly difficult. Furthermore, many state-of-the-art deep learning methods are limited to 2-D image data, making application to 3-D digital outcrops (e.g., hyperclouds) an outstanding challenge.
The Tinto dataset aims to help solve these validation issues and so foster further development of deep learning techniques in the geosciences. It comprises two representations (tinto2D and tinto3D) of three benchmark datasets: a real one, a noise-free and realistic (degraded) synthetic twin.

The real dataset (tinto.real) comprises a compilation of visible, near, short-wave and long-wave infrared hyperspectral data acquired using ground and airborne sensors at Rio Tinto, Spain. These have been corrected for atmospheric and topographic effects, and projected onto a photogrammetric point cloud to derive a set of hyperclouds (tinto3D) and corresponding 2D views (tinto2D). Ground-truth labels for every point in the hypercloud (and by projection every pixel in tinto2D) were then derived by a combination of laboratory XRD analyses, hyperspectral interpretation, and digital outcrop mapping.

Issues associated with potential biases or inconsistencies in the ground-truth labels associated with the real dataset have been addressed by generating an entirely synthetic suite of spectral data by forward modelling (tinto.synth and tinto.degr). These share the same labels as the real dataset, as well as several latent variables and spatial relationships, but are derived using a spectral mixing model and a spatial distribution of mineral abundances simulated using spectral proxies. We suggest that these synthetic spectra are suited for comparing learning approaches, as the ground truth is known with certainty, while the real spectra can be used to evaluate performance on realistic data. tinto.synth contains perfect (noise-free) spectra, largely for testing purposes, while tinto.degr contains these spectra with added sensor-noise, illumination and topographic effects to better simulate real data. Synthetic mineral abundances and pure end-member spectra have also been included in tinto.synth for testing e.g., endmember extraction and unmixing methods.

Finally, we have also included two versions of the ground-truth labels for each dataset: one simplified (tinto.labels_basic), and one complete (tinto.labels_complete). While we encourage people to use the complete label set, geologically similar classes have been lumpted together in the basic dataset to derive a benchmark with fewer classes for testing e.g., unsupervised methods.

## Citation

If the Tinto dataset is useful for your work, please cite:

> [Afifi, Ahmed J., et al. “Tinto: Multisensor Benchmark for 3D Hyperspectral Point Cloud Segmentation in the Geosciences.” IEEE Transactions on Geoscience and Remote Sensing (2023). 10.1109/TGRS.2023.3340293](https://dx.doi.org/10.1109/TGRS.2023.3340293)