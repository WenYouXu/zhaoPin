<template>
    <div>
        <div id="baidumap" class="map"></div>
    </div>
</template>

<script>
export default{
    name:'map',
    mounted(){
        var map = new BMap.Map("map"); // 创建Map实例
        map.centerAndZoom(new BMap.Point(104.07258, 30.550701), 20); // 初始化地图,设置中心点坐标和地图级别
        //添加地图类型控件
        map.addControl(
        new BMap.MapTypeControl({
            mapTypes: [BMAP_NORMAL_MAP, BMAP_HYBRID_MAP],
        })
        );
        map.setCurrentCity("成都"); // 设置地图显示的城市 此项是必须设置的
        map.enableScrollWheelZoom(true);
    }
}
</script>

<style scoped>
.baidumap{
    height: 600px;
    width: 100% ;
}
</style>