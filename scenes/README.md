
### Scene Format

To train ADOP on your scene you must convert it to the following format. If you have reconstructed the scene with COLMAP you can use the COLMAP2ADOP converter below.

```
+ scenes/my_dataset/
  - dataset.ini [required]
        Copy this from a sample scene and update the pathes.
  - Camera files [required]
        For each camera one ini file. Checkout sample scenes.
        If all images are captured by the same camera, only one camera file is required!
        camera0.ini
        camera1.ini
        ... 
  - point_cloud.ply [required]
        positions, normals
  - images.txt      [required]
        0000.jpg
        0001.jpg
        ...
  - camera_indices.txt [required]
        For each image the corresponding camera. Example:
        0
        0
        1
        0
        ... 
  - masks.txt [optional]
        0000.png
        0001.png
        ...
  - poses.txt [required]
        Camera -> World Transformation
        qx qy qz qw tx ty tz
   - exposure.txt [optional]
        Initialization of the Exposure Value (EV). For example from the jpg EXIF data.
        13.1
        14
        10.5
        ...
```

### Import COLMAP Scenes

All of our sample scenes have been generated by COLMAP.
To run ADOP on your COLMAP reconstruction use the colmap2adop executable.

Usage:

```shell
<build_dir>/bin/colmap2adop 
```