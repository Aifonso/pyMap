# pyMap

Raster Map Download Helper

## Similar Project

 - [brandonxiang/pyMap](https://github.com/brandonxiang/pyMap) Raster Map Download Helper by python.
 - [brandonxiang/pyMap_GFW](https://github.com/brandonxiang/pyMap_GFW) Raster Map Download Helper with [selenium](https://github.com/SeleniumHQ/selenium/) and [PhantomJS](http://phantomjs.org/)
 - [brandonxiang/pyMap_webapp](https://github.com/brandonxiang/pyMap_webapp) A webapp version for [pyMap]((https://github.com/brandonxiang/pyMap)
 - [brandonxiang/nodemap_spider](https://github.com/brandonxiang/nodemap_spider) Crawler Project for Raster Map by Electron.
 - [brandonxiang/nodemap](https://github.com/brandonxiang/nodemap) A electron app for [nodemap_spider](https://github.com/brandonxiang/nodemap_spider)

这是一个简单的实例，去实现地图下载工具。如今又很多瓦片的下载工具，但是都是收费的，感觉既然是盗版还要收费，非常不好。我决定做一个简单的地图下载器，将瓦片下载拼接成对应的图片。

经供参考，不要从事商业用途，后果自负。

## 依赖

- python3.5
- requests 负责下载功能
- pillow 负责图片拼接
- tqdm 负责进度条

## 安装

1. 安装python3.5

2. 安装对应的第三方库

```
pip install -r requirement.txt
```

## 用法

### 配置文件

配置文件格式

如果使用瓦片编码下载

```
[config]
下载方式 = 瓦片编码
左上横轴 = 803
左上纵轴 = 984
右下横轴 = 857
右下纵轴 = 1061
级别 = 8
项目名 = test
地图地址 = default
```

如果使用地理编码下载

```
[config]
下载方式 = 地理编码
左上横轴 = 113.889962
左上纵轴 = 22.456671
右下横轴 = 114.212686
右下纵轴 = 22.345576
级别 = 13
项目名 = sample
地图地址 = gaode
```


### 运用命令行

```
python pyMap.py 22.456671 113.889962 22.345576 114.212686 13 sample gaode
```

- 参数1： 西北角纬度
- 参数2： 西北角经度
- 参数3： 东南角纬度
- 参数4： 东南角经度
- 参数5： 比例尺级别
- 参数6： 输出路径（默认'output/mosaic.png'）
- 参数7： 地图类型（默认'gaode.image'）

### 硬编码

请自修修改，下面是通过经纬度下载数据。

```
def test():
    process_latlng(22.4566710000, 113.8899620000, 22.3455760000, 114.2126860000, 13)
```

或者通过瓦片编号下载数据。

```
def test():
    process_tilenum(1566, 1788, 1976, 2149, 9, "output/overlay.png")
```

## License

[MIT](LICENSE)
