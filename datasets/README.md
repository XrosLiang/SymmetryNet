## Data format

### RGB-D images:
**ShapeNet**:
The SymmetryNet data of ShapeNet is organized by the subset division. The data of each subset is stored under folders named <holdout_view>, <holdout_instance> or <holdout_category>. In each folder, the RGB-D images are stored under <class_folder>/<instance_folder>. Each RGB image contains the following files:
```shell
|-- <subset_folder>
|---- <class_folder>
|------ <instance_folder>
|-------- <view_id-color-crop.png>
          rendered color image
|-------- <view_id-depth-crop.png>
          rendered depth image
|-------- <view_id-rt.txt>
          extrinsic parameters
|-------- <view_id-k-crop.txt>
          intrinsic parameters
|-------- <view_id-color-crop-occlusion.png>
          rendered color image with occlusion
|-------- <view_id-depth-crop-occlusion.png>
          rendered depth image with occlusion
|-------- <view_id-occlusion.txt>
          occlusion ratio
The scale factor of depth image is 100.
```

**ScanNet**:
The data of each subset is stored under folders named <holdout_view> or <holdout_scene>. In each folder, the RGB-D images are stored under <subset_folder>/<scene_folder>. Each RGB image contains the following files:
```shell
|-- <subset_folder>
|---- <scene_folder>
|------ <view_id-color.jpg>
        color image
|------ <view_id-depth.png>
        depth image
|------ <view_id-label.png>
        object segmentation labels
|------ <view_id-meta.mat>
        other RGB-D information, the format is similar to the format of YCB
```

**YCB**:
The format of SymmetryNet data of YCB is the same to [PoseCNN][1].


### Symmetry annotations:
We provide the object-level symmetry annotation. The format is:
~~~~ 
object_center_x object_center_y object_center_z
ref_sym1_normal_x ref_sym1_normal_y ref_sym1_normal_z
ref_sym2_normal_x ref_sym2_normal_y ref_sym2_normal_z
ref_sym3_normal_x ref_sym3_normal_y ref_sym3_normal_z
rot_sym_direction_x rot_sym_direction_y rot_sym_direction_z
~~~~
The symmetry is invalid (not exist) when the normal or the direction is (0, 0, 0).

[1]:  https://rse-lab.cs.washington.edu/projects/posecnn/ "PoseCNN"


