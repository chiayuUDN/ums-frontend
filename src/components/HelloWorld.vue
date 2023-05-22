<template>
    <div class="hello-world">
      <div class="box">
          <i class="bi bi-person-check"></i>
          <i class="bi bi-bag-check-fill"></i>
          <i class="bi bi-ui-checks"></i>
          <button type="button" class="btn btn-primary">Primary</button>
      </div>
    </div>
  
    <lineChart></lineChart>
    <barChart></barChart>
    <pieChart></pieChart>
</template>
<script>
import lineChart from './echarts/lineChart.vue';
import barChart from './echarts/barChart.vue';
import pieChart from './echarts/pieChart.vue';

export default {
    components: {
        lineChart,
        barChart,
        pieChart
    },
    props: {
        msg: String,
    },
    data() {
        return {
            count: 0
        }
    }

}
</script>

<style lang="scss" scoped>
    .hello-world {
        .box {
            width: 400px;
            height: 200px;
            background-color: aquamarine;
        }
    }
</style>