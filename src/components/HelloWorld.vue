<template>
    <lineChart :data="data_array[0]"></lineChart>
    <areaChart :data="data_array[0]"></areaChart>
    <barChart :data="data_array[0]"></barChart>
    <pieChart :data="data_array[0]"></pieChart>
</template>
<script>
import lineChart from './echarts/lineChart.vue';
import areaChart from './echarts/areaChart.vue';
import barChart from './echarts/barChart.vue';
import pieChart from './echarts/pieChart.vue';
import dayjson from './jsonData/day/InsightX Content.json';

export default {
    components: {
        lineChart,
        areaChart,
        barChart,
        pieChart
    },
    props: {
        msg: String,
    },
    data() {
        return {
            data_array: null
        }
    },
    created() {
        this.data_array = [
            {
                "2023-04-01": "4946",
                "2023-04-02": "4575",
                "2023-04-03": "4580",
                "2023-04-04": "4991",
                "2023-04-05": "4857"
            }
        ];
    }
}
</script>