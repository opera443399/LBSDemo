# LBSDemo

> from: https://github.com/opera443399/eviltransform


### 新建 ios xcode 项目
新增文件： Location.gpx

```xml
<?xml version="1.0"?>
<gpx version="1.1" creator="Xcode">

    <!--
     Provide one or more waypoints containing a latitude/longitude pair. If you provide one
     waypoint, Xcode will simulate that specific location. If you provide multiple waypoints,
     Xcode will simulate a route visiting each waypoint.
     -->
    <wpt lat="33.546411767782338" lon="223.95348721621627">
    </wpt>

</gpx>

```

### eviltransform 坐标点转换
```go
package main

import (
    "fmt"
    trans "github.com/eviltransform"
)

func main() {
    fmt.Printf("Hello\n")
    gcjLat := 33.543428
    gcjLng := 223.958387
    wgsLat, wgsLng := trans.GCJtoWGS(gcjLat, gcjLng)
    fmt.Printf("wgsLat=%v\n", wgsLat)
    fmt.Printf("wgsLng=%v\n", wgsLng)
}
```



### ZYXW、参考
1. [SimulateLocation](https://github.com/RockerHX/SimulateLocation)
2. [eviltransform](https://github.com/googollee/eviltransform)
