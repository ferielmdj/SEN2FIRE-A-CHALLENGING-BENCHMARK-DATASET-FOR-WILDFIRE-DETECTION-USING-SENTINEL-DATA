# SEN2FIRE-A-CHALLENGING-BENCHMARK-DATASET-FOR-WILDFIRE-DETECTION-USING-SENTINEL-DATA
in our project theres 11 modes (check train.py inside the base_code):

| Mode ID | Mode Name                   | Input Description                             | #Channels |
| ------: | --------------------------- | --------------------------------------------- | --------- |
|       0 | `all_bands`                 | All Sentinel-2 spectral bands                 | 12        |
|       1 | `all_bands_aerosol`         | All Sentinel-2 bands + aerosol                | 13        |
|       2 | `rgb`                       | RGB bands only (B4, B3, B2)                   | 3         |
|       3 | `rgb_aerosol`               | RGB + aerosol                                 | 4         |
|       4 | `swir`                      | SWIR bands                                    | 3         |
|       5 | `swir_aerosol`              | SWIR + aerosol                                | 4         |
|       6 | `nbr`                       | Normalized Burn Ratio (NBR)                   | 3         |
|       7 | `nbr_aerosol`               | NBR + aerosol                                 | 4         |
|       8 | `ndvi`                      | Normalized Difference Vegetation Index (NDVI) | 3         |
|       9 | `ndvi_aerosol`              | NDVI + aerosol                                | 4         |
|      10 | `rgb_swir_nbr_ndvi`         | Fusion of RGB, SWIR, NBR, NDVI                | 6         |
|      11 | `rgb_swir_nbr_ndvi_aerosol` | Full fusion + aerosol                         | 7         |



we'll just be using mode 3 and mode 1 , most accurate to our needs. ( we add aerosol cz it gives better results )


#  Quantitative Results:

##   Mode 1 : All Bands + Aerosol (all_bands_aerosol including NIR)
### Training / Validation
| Metric                | Fire Class (%) |
| --------------------- | -------------- |
| Precision             | **39.44**      |
| Recall                | **37.92**      |
| IoU                   | **23.97**      |
| F1-score              | **38.66**      |
| mIoU                  | **68.23**      |
| Overall Accuracy (OA) | **95.73**      |

### Testing
| Metric                | Fire Class (%) |
| --------------------- | -------------- |
| Precision             | **22.24**      |
| Recall                | **15.33**      |
| IoU                   | **9.98**       |
| F1-score              | **18.15**      |
| mIoU                  | **56.98**      |
| Overall Accuracy (OA) | **92.01**      |

### Time Inference
| Property           | Value                                     |
| ------------------ | ----------------------------------------- |
| Avg inference time | **0.0048 s / patch**                      |
| FPS                | **≈ 208 FPS**                             |

##   Mode 3 : RGB + Aerosol
### Training / Validation
| Metric                | Fire Class (%) |
| --------------------- | -------------- |
| Precision             | **10.74**      |
| Recall                | **26.30**      |
| IoU                   | **8.26**       |
| F1-score              | **15.25**      |
| mIoU                  | **54.86**      |
| Overall Accuracy (OA) | **89.62**      |

### Testing
| Metric                | Fire Class (%) |
| --------------------- | -------------- |
| Precision             | **6.01**       |
| Recall                | **3.29**       |
| IoU                   | **2.17**       |
| F1-score              | **4.25**       |
| mIoU                  | **49.88**      |
| Overall Accuracy (OA) | **91.44**      |

### Time Inference
| Property           | Value                 |
| ------------------ | --------------------- |
| Avg inference time | **0.00375 s / patch** |
| FPS                | **≈ 266 FPS**         |
