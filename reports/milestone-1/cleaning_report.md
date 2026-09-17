# Dataset Cleaning Report

## Original Dataset

Total images: 1189

## Quality Checks

Corrupted images: 0

Non-image files: 0

Duplicate groups: 48

Duplicate files identified: 49

Cross-class duplicate groups: 0

## Manually Flagged Images

| File | Class | Reason |
|---|---|---|
| 218b.jpg | Black_Soil | Insufficient clear soil region / distracting background |

## Cleaning Policy

The raw dataset will remain unchanged.

Duplicate copies and manually flagged unusable images will be excluded from the processed dataset.

One copy from each duplicate group will be retained.
## Final Cleaning Results

Original image count: 1189

Duplicate copies excluded: 49

Manually flagged images excluded: 1

Final processed image count: 1139

Cross-class duplicate groups: 0

Corrupted images: 0

Non-image files: 0

## Final Processed Class Distribution

| Class | Images |
|---|---:|
| Alluvial_Soil | 50 |
| Arid_Soil | 279 |
| Black_Soil | 233 |
| Laterite_Soil | 214 |
| Mountain_Soil | 191 |
| Red_Soil | 107 |
| Yellow_Soil | 65 |
| Total | 1139 |
## Image Preprocessing

The cleaned dataset containing 1,139 images was processed using an OpenCV-based preprocessing pipeline.

### Preprocessing Steps

1. Image loading using OpenCV
2. BGR to RGB conversion
3. LAB color-space conversion
4. CLAHE-based local contrast enhancement
5. Aspect-ratio-preserving resizing
6. Padding to 224 × 224 pixels
7. Saving standardized PNG images

### Background Handling

HSV thresholding and GrabCut were evaluated experimentally.

HSV thresholding did not reliably isolate soil regions.

GrabCut performed well on some images but removed important soil regions in several other classes.

Therefore, aggressive automatic background removal was not applied globally. The final pipeline preserves soil information while avoiding unreliable segmentation.

### Final Dataset

Total cleaned images: 1,139

Total preprocessed images: 1,139

Failed preprocessing: 0