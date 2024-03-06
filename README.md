# waymo2kitti

Waymo dataset V1.1 to KITTI dataset convertion notes:

Warning: Based on the Waymo dataset agreement, the converted data can only be used for non-commercial purposes.

Support for other Waymo dataset versions is not guaranteed.

Also, Waymo V2.0 dataset changed the format completely, so the method here will not work for V2.0 without significant changes.


## steps

1. Download the Waymo dataset V1.1

2. git clone https://github.com/abhi1kumar/DEVIANT.git

3. refer to https://github.com/abhi1kumar/DEVIANT/blob/main/data/data_setup_README.md to set up data conversion environment

```
# Set up environment
conda create -n py36_waymo_tf python=3.7
conda activate py36_waymo_tf
conda install cudatoolkit=11.3 -c pytorch

# Newer versions of tf are not in conda. tf>=2.4.0 is compatible with conda.
pip install tensorflow-gpu==2.4
conda install pandas
pip3 install waymo-open-dataset-tf-2-4-0 --user

```

4. refer to https://github.com/abhi1kumar/DEVIANT/blob/main/data/data_setup_README.md to run the conversion script


* Note: the conversion code included in DEVIANT commented out the line
https://github.com/abhi1kumar/DEVIANT/blob/009955f3bbb21c38a687eaae59bdfcb82eca93e7/data/waymo/converter.py#L135-L136

```
            # save images
            # self.save_image(frame, file_idx, frame_idx)
```

* if you need lidar data, you can uncomment the line