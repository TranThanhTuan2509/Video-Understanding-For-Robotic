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
