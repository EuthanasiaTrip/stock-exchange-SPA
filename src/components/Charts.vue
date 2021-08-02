<template>
  <div>
      <h1>Котировки</h1>
      <v-card class="graph-card">
        <div class="graph">
          <canvas ref="canvas"></canvas>
        </div>
      </v-card>
  </div>
</template>

<script>
import { Line } from "vue-chartjs"

export default {
  name: "Charts",
  extends: Line,
  data() {
    return {
      datacollection: null
    }
  },
  mounted() {
      this.renderChart({
        labels: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11'],
        datasets:[
            {
              label: 'Data One',
              borderColor: '#FF8F00',
              backgroundColor: '#FFE0B2',
              data: [6, 3, 5, 2, 4, 7, 9, 11, 1, 2, 8],
              lineTension: 0
            },
        ]
        }, {responsive: true})
    }
}
</script>

<style lang="scss" scoped>
.graph-card{
  width: 60%;
  height: 70%;
  margin: 25px;
}
.graph{
  width: 90%;
  height: 70%;
}
</style>
