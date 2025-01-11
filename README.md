# Video-Understanding-For-Robotic

## Environment & Compilation

Create a new conda environment:
```
conda create -n videou python=3.8

```
```
pip install -r requirements.txt
```
I recommend that users follow the best practices to install MMAction2:
```
pip install -U openmim
mim install mmcv==2.0.0
mim install mmdet==3.0.0
mim install mmengine==0.7.2
```

Install all the python dependencies using pip:
```
pip install -r requirements.txt
```

Download a pretrained-weight for detection model, save downloaded checkpoint inside `hand_object_detector/res101_handobj_100K/pascal_voc` folder:
<table><tbody>
<tr>
<td align="center">Name</td>
<td align="center">Hand</td>
<td align="center">Obj</td>
<td align="center">H+Side</td>
<td align="center">H+State</td>
<td align="center">H+O</td>
<td align="center">All</td>
<td align="center">Model Download Link</td>
</tr>

<tr>
<td align='left'>handobj_100K+ego</td>
<td align='center'>90.4</td>
<td align='center'>66.3</td>
<td align='center'>88.4</td>
<td align='center'>73.2</td>
<td align='center'>47.6</td>
<td align='center'>39.8</td>
<td align="center"><a href="https://drive.google.com/open?id=1H2tWsZkS7tDF8q1-jdjx6V9XrK25EDbE">faster_rcnn_1_8_132028.pth</a></td>
</tr>

</tbody></table>

Save the downloaded file to your own specified directory, you have to update the --dest `hand_object_detector/mmaction2/pretrained_file_and_checkpoint`:
```
mim download mmaction2 --config tsn_imagenet-pretrained-r50_8xb32-1x1x8-100e_kinetics400-rgb --dest /path
```

Compile the cuda dependencies using following simple commands:
```
cd lib
python setup.py build develop
```
Run the main code:
```
python3 demo.py --checkepoch=8 --checkpoint=132028 --video /home/tuan/Downloads/picking_cube.mp4
```
Predicted command is saved in `motion_saver` folder
