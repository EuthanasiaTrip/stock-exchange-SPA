<template>
  <div>
      <h1>Графики</h1>
      <span>
        <v-card class="graph-card">
          <div class="graph">
            <canvas ref="canvas"></canvas>
          </div>
        </v-card>
      </span>
      <span>
        <stocks-table class="content-table"
          :cardHeight="530"
        ></stocks-table>
      </span>
  </div>
</template>

<script>
import { Line } from "vue-chartjs"
import StocksTable from "./StocksTable.vue"

export default {
  name: "Charts",
  components: {
    StocksTable
  },
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
  display: inline-block;
  width: 60%;
  position: relative;
  top: 15px;
  padding: 2%;
}
.graph{
  width: 90%;
  height: 70%;
}
.content-table{
  display: inline-block;
  width: 30%;
  margin-left: 2%;
  position: relative;
}
</style>
