使用百度地图js api 2.0, 使用polygon的时候，发现创建polygon之后在加入到地图图层之前就开始编辑模式，就不能创建第二个polygon，如下面代码(coffee写的，不完整):
```
points = [
            new BMap.Point((point.lng + 0.002), (point.lat + 0.002)),
            new BMap.Point((point.lng + 0.002), (point.lat - 0.002)),
            new BMap.Point((point.lng - 0.002), (point.lat - 0.002)),
            new BMap.Point((point.lng - 0.002), (point.lat + 0.002))
          ]

          polygon = new BMap.Polygon points, $scope.polygonOptions
          polygon.enableEditing() # 当在map.addOverlay之前添加启动编辑模式
          map.addOverlay polygon

          polygon = new BMap.Polygon points, $scope.polygonOptions
          polygon.enableEditing() # 第二次再创建polygon又要开始编辑模式的时候，就会出现`Uncaught TypeError: Cannot read property 'Ia' of null`错误
          map.addOverlay polygon        

```

正确的写法是:
```
map.addOverlay polygon # 先将polygon添加到地图的图层上，然后再开启编辑模式
polygon.enableEditing()
```