# LBSDemo
2018/12/3


### 转换坐标
**eviltransform 坐标点转换的方法示例**
Transform coordinate between earth(WGS-84) and mars in china(GCJ-02).
GCJ-02 coordiante is used by Google Maps, Autonavi Map and other china map service. (Baidu Map has an extra offset based on GCJ-02)


```go
$ cat app.go
package main

import (
    "fmt"
    trans "github.com/eviltransform"
)

func main() {
    gcjLat := 22.488375
    gcjLng := 113.952356
    wgsLat, wgsLng := trans.GCJtoWGS(gcjLat, gcjLng)
    fmt.Println(wgsLat, wgsLng)}

$ go run app.go
22.491374082616236 113.9474699156593

```


```python
$ sudo pip install eviltransform
$ python -c 'import eviltransform; print(eviltransform.gcj2wgs(22.488375, 113.952356))'
(22.491374082616236, 113.9474699156593)

```


### 新建 xCode 项目
添加 gpx 文件到项目中： sz.gpx

**内容如下**
```xml
<?xml version="1.0"?>
<gpx version="1.1" creator="Xcode">
    <wpt lat="22.491374082616236" lon="113.9474699156593">
    </wpt>
</gpx>

```

### 激活模拟
**菜单**
Edit Scheme -> Run(Debug) -> Options -> Default Location(sz)


### FAQ
**为何app运行后，地址仍然没有变化？**
请检查gpx地址是否有效，如果是一个无效的地址，将模拟失败



### ZYXW、参考
1. [SimulateLocation](https://github.com/RockerHX/SimulateLocation)
2. [eviltransform](https://github.com/googollee/eviltransform)
3. [Autonavi-lbs]https://lbs.amap.com/console/show/picker
