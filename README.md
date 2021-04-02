# Pneumonia-Diagnosis-using-X-Ray
Based on artificial intelligence (machine learning) approaches I built a computer-aided diagnosis system that helps radiologists to identify pneumonia cases by X-Ray images.
# Data Introduction
  The data is from @Kaggle (https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia) ( The original data sets is from here ). But here we just use kaggle's data to analysis.
  There are two category in kaggle's data sets : Normal and PNEUMONIA (PEUMONIA can also split into virus and bacteria, but currently we just consider Normal & PNEUMONIA to study)
  
  ![image](https://user-images.githubusercontent.com/81783919/113368830-552fa600-9368-11eb-8cda-e89e542c557c.png)
# Data explore
The kaggle's data have split data set into 3 folders : train、val and test.
The train folder totally have 5216 jpg files (Normal:1341，PNEUMONIA:3875).
The val folder totally have 16 jpg files (Normal:8，PNEUMONIA:8).
The test folder totally have 624 jpg files (Normal:234，PNEUMONIA:390).
Remark! The train folder is an imbalance data sets for Normal & PNEUMONIA (about 1:3)

# Model Build
I use xception model with transfer learning.
```
image_data_generator(
  rescale            = 1/255    ,
  rotation_range     = 5        ,
  width_shift_range  = 0.1      ,
  height_shift_range = 0.05     ,
  shear_range        = 0.1      ,
  zoom_range         = 0.15     ,
  horizontal_flip    = TRUE     ,
  vertical_flip      = FALSE    ,
  fill_mode          = "reflect"
)
```

