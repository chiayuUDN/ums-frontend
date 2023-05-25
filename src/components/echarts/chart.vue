<template>
    <div ref="chart" class="chart-container"></div>
</template>
<script>
import * as echarts from 'echarts';

export default {
    props: {
        // 圖形參數
        option: {
            type: Object,
            default: () => {}
        },
        // 設定圖形寬高
        size: Object
    },
    data() {
        return {
            chartX: null
        }
    },
    methods: {
        initChart() {
            // 初始化圖表，指定容器
            var drawChart = echarts.init(this.$refs.chart);
            
            // 設置圖表的配置選項和數據
            drawChart.setOption(this.option);
            window.addEventListener('resize', function() {
                drawChart.resize();
            });
        }
    },
    watch: {
        option() {
            this.initChart();
        }
    },
    mounted() {
        this.initChart();
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