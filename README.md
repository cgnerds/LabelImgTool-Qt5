# LabelImg

[![Build Status](https://travis-ci.org/lzx1413/labelImgPlus.svg?branch=master)](https://travis-ci.org/lzx1413/labelImgPlus)

LabelImg is a graphical image annotation tool.

It is written in Python and uses Qt for its graphical interface.

The annotation file will be saved as an XML file. The annotation format is PASCAL VOC format, and the format is the same as [ImageNet](http://www.image-net.org/)

task mode change

![](screenshot/setting_panel.jpg)

DET mode

![](screenshot/bbox_label.jpg)

SEG mode

![](screenshot/parse_label.jpg)

CLS mode

![](screenshot/cls_task.jpg)


## Build source and use it

Requires at least [Python 3.10](http://www.python.org/getit/) and has been tested with [PyQt5.15](http://www.riverbankcomputing.co.uk/software/pyqt/intro).

* Ubuntu
``` bash
conda create -n labelimgtool python=3.10 -y
conda activate labelimgtool
pip install -r requirements.txt
python labelImgTool.py
# (If UI is not right, run this. Or, ignore it.)
pyrcc5 -o resources.py resources.qrc
```
## Default file framework

|---Images

​         |---images_1

​         |---images_2

|---Annotation

​          |---images_1

​          |---images_2        

the file containing annotations will be created by default.

## Usage
For usage instructions you can see [Here](https://youtu.be/p0nR2YsCY_U)

At the moment annotations are saved as an XML file. The format is PASCAL VOC format, and the format is the same as [ImageNet](http://www.image-net.org/)

You can also see [ImageNet Utils](https://github.com/tzutalin/ImageNet_Utils) to download image, create a label text for machine learning, etc

### Label and  parsing

support rectangle label and parsing labels

### Create pre-defined classes

You can edit the [data/predefined_classes.txt](https://github.com/tzutalin/labelImg/blob/master/data/predefined_classes.txt) to load pre-defined classes

You also can create labels with two levels in [data/predefined_sub_classes.txt](https://github.com/lzx1413/labelImg/blob/master/data/predefined_sub_classes.txt) 

And the labels will be ranked by the frequency you use it.

### General steps from scratch

* Click 'Change default saved annotation folder' in Menu/File

* Click 'Open Dir'

* Click 'Create RectBox'

The annotation will be saved to the folder you specifiy

### Hotkeys

* Ctrl + r : Change the defult target dir which saving annotation files

* Ctrl + n : Create a bounding box

* Ctrl + s : Save

* Right : Next image

* Left : Previous image

### Online image data mode

the server have to make the images in a folder that clint can get from http/https with **get** function

* settings

open File -->RemoteDBSettings(ctrl+m) like that

![](screenshot/remote_settings.JPG)

the remote image list is a file contenting the name of the images (a line is a image) .

the image will be cached in a folder created in the software file named database/pics/XXXX and this will take a lot of memory if there are a lot of images,and this will be modified in the future.

open File   -->ChangedDefaultSavedAnnotationDir(ctrl+r) to set the folder to save the results

2. if your settings are right,you will find the **Get Images** button becomes enabled and click it ,then you can annotate the images as before
