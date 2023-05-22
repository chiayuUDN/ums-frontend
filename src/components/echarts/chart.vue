<template>
    <div ref="chart" class="chart"></div>
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
        chart() {
            const chart = echarts.init(this.$refs.chart);
            chart.setOption(this.option);
            window.addEventListener('resize', function() {
                chart.resize();
            });
        }
    },
    mounted() {
        this.chart();
    }
}
</script>
<style lang="scss" scoped>
    .chart {
        width: 100%;
        height: 400px;
    }
</style>