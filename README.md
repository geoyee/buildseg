# buildseg
[![Python 3.8](https://img.shields.io/badge/python-3.8-red.svg)](https://www.python.org/downloads/release/python-360/) [![PaddlePaddle 2.2](https://img.shields.io/badge/paddlepaddle-2.2-green.svg)](https://www.python.org/downloads/release/python-360/) [![QGIS 3.16.11](https://img.shields.io/badge/qgis-3.16.11-blue.svg)](https://www.python.org/downloads/release/python-360/)

buildseg is a building extraction plugin of QGIS based on PaddlePaddle.

![gsdkjl](https://user-images.githubusercontent.com/71769312/144696383-6701eb99-1a4f-4403-93df-5ab4fac801d3.gif)

## How to use
1. Download and install [QGIS](https://www.qgis.org/en/site/) and clone the repo:

``` git
git clone git@github.com:geoyee/buildseg.git
```

2. Enter the folder and install dependent libraries using OSGeo4W shell:

``` shell
cd buildseg
pip install -r requirements.txt
```

3. Copy folder named buildseg in QGIS configuration folder(?\default\python\plugins) and reload plugin.

4. Open QGIS and load raster, and use the plugin to select the parameter file(*.pdiparams).

## Model and Parameter

| Model  | Backbone  | Resolution |  mIoU  | Params(MB) | Inference Time(ms) |                            Links                             |
| :----: | :-------: | :--------: | :----: | :--------: | :----------------: | :----------------------------------------------------------: |
| OCRNet | HRNet_W18 |  512x512   | 90.64% |    46.4    |         /          | [Static Weight](https://cloud.a-boat.cn:2021/share/3xda5wmV) |

- Train/Eval Dataset: [Link](https://aistudio.baidu.com/aistudio/datasetdetail/102929).
- Inference Environment: Tesla V100 32G in AI Studio.

## TODO

- [x] Extract building on 512x512 remote sensing images.
- [x] Extract building on big remote sensing images through sliding frame and splicing.
- [x] Replace the model and parameters (large-scale data).
- [x] Convert to static weight.
- [x] Add a Jupyter Notebook(*.ipynb) about how to fine-tune it used other's dataset based on  PaddleSeg.
- [ ] Hole digging inside polygon.
- [ ] Convert raster to shapefile by GIS instead of findContours in OpenCV.
- [ ] Update plugin's UI.
- [ ] Accelerate, etc.
- [ ] Add another model, like Vision Transform.

