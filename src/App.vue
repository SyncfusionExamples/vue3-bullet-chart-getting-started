<template>
  <ejs-bulletchart :dataSource="data" :valueField="valueField" :tooltip="tooltip" :targetField="targetField" :height="height"
    :title="title" :minimum="minimum" :maximum="maximum" :interval="interval">
    <e-bullet-range-collection>
      <e-bullet-range end="100" color="red"></e-bullet-range>
      <e-bullet-range end="200" color="blue"></e-bullet-range>
      <e-bullet-range end="300" color="green"></e-bullet-range>
    </e-bullet-range-collection>
  </ejs-bulletchart>
</template>

<script>
import { BulletChartComponent, BulletTooltip, BulletRangeCollectionDirective, BulletRangeDirective } from "@syncfusion/ej2-vue-charts";

export default {
  components: {
    "ejs-bulletchart": BulletChartComponent,
    "e-bullet-range-collection": BulletRangeCollectionDirective,
    "e-bullet-range": BulletRangeDirective
  },
  data() {
    return {
      data: [
        { value: 100, target: 80 },
        { value: 200, target: 180 },
        { value: 300, target: 280 },
        { value: 400, target: 180 },
        { value: 500, target: 230 }
      ],
      minimum: 0,
      maximum: 300,
      interval: 50,
      tooltip: { enable: true },
      title: 'Revenue',
      height: '300px',
      targetField: 'target',
      valueField: 'value'
    };
  },
  provide: {
    bulletChart: [BulletTooltip]
  },
};
</script>