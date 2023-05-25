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
    data() {
        return {
            chartObj: null,
        }
    },
    methods: {
        initChart() {
            if(this.chartObj) echarts.dispose(this.chartObj);

            // 初始化圖表，指定容器
            this.chartObj = echarts.init(this.$refs.chart); 
            // 設置圖表的配置選項和數據
            this.chartObj.setOption(this.option);
            window.addEventListener('resize', function() {
                this.chart.resize();
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