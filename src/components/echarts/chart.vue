<template>
    <div ref="chart" class="chart-container"></div>
</template>
<script>
import * as echarts from 'echarts';

export default {
    props: {
        // 圖形參數
        option: Object,
        // 設定圖形寬高
        size: Object
    },
    methods: {
        initChart() {
            // 初始化圖表，指定容器
            var chartObj = echarts.init(this.$refs.chart); 
            // 設置圖表的配置選項和數據
            chartObj.setOption(this.option);
            window.addEventListener('resize', function() {
                chartObj.resize();
            });
        },
    },
    mounted() {
        this.initChart();
    },
    watch: {
        option() {
            this.initChart();
        }
    }
}
</script>
<style lang="scss" scoped>
    .chart-container {
        width: 100%;
        height: 400px;
    }

    @media screen and (max-width: 768px) {
        .chart-container {
            height: 300px;
        }
    }

    @media screen and (max-width: 480px) {
        .chart-container {
            height: 200px;
        }
    }
</style>