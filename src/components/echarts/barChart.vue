<!-- 長條圖 -->
<template>
    <chart :option="option"></chart>
</template>
<script>
import chart from './chart.vue';

export default {
    components: { chart },
    data() {
        return {
            option: {},
        }
    },
    created() {
        this.option = {
            title: {
                left: 'center',
                text: 'Stacked Bar'
            },
            tooltip: {
                trigger: 'axis'
            },
            legend: {
                top: 30,
                data: ['Email', 'Union Ads', 'Video Ads', 'Direct', 'Search Engine']
            },
            grid: {
                left: '3%',
                right: '4%',
                bottom: '3%',
                containLabel: true
            },
            toolbox: {
                feature: {
                saveAsImage: {}
                }
            },
            xAxis: {
                type: 'category',
                boundaryGap: false,
                data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
            },
            yAxis: {
                type: 'value'
            },
            series: [
                {
                name: 'Email',
                type: 'bar',
                stack: 'Total',
                data: [120, 132, 101, 134, 90, 230, 210]
                },
                {
                name: 'Union Ads',
                type: 'bar',
                stack: 'Total',
                data: [220, 182, 191, 234, 290, 330, 310]
                },
                {
                name: 'Video Ads',
                type: 'bar',
                stack: 'Total',
                data: [150, 232, 201, 154, 190, 330, 410]
                },
                {
                name: 'Direct',
                type: 'bar',
                stack: 'Total',
                data: [320, 332, 301, 334, 390, 330, 320]
                },
                {
                name: 'Search Engine',
                type: 'bar',
                stack: 'Total',
                data: [820, 932, 901, 934, 1290, 1330, 1320]
                }
            ]
        }
    }
}
</script>
<style lang="scss" scoped>
    .bar-chart {
        width: 100%;
        height: 400px;
    }
</style>