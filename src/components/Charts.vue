<template>
  <div>
      <h1>Графики</h1>
      <span>
        <v-card class="graph-card">
          <div class="graph">
            <canvas ref="canvas"></canvas>            
          </div> 
          <v-btn
          @click="applyFilter(1)"
          >
          тык
          </v-btn>                
        </v-card>        
      </span>
      <span>
        <stocks-table class="content-table"
          :cardHeight="530"
          :hideFooter="false"          
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
      datacollection: null,
      chartData: [
        {x: '2021-08-01', y: 10},
        {x: '2021-08-05', y: 5},
        {x: '2021-08-10', y: 12},
        {x: '2021-08-15', y: 9},
        {x: '2021-08-20', y: 14},
        {x: '2021-08-22', y: 20},
        {x: '2021-08-23', y: 16},
        {x: '2021-08-27', y: 17},
        {x: '2021-08-30', y: 14},
        {x: '2021-09-01', y: 21},
        {x: '2021-09-10', y: 19}
        ],
      chartInfo: {
        type: 'time',
        datasets:[
            {
              label: 'Data One',
              borderColor: '#FF8F00',
              backgroundColor: '#FFE0B2',
              data: this.chartData,
              lineTension: 0
            },
        ]
        },
      chartOptions: {
          responsive: true,
          scales: {
            xAxes: [
              {
                type: "time",
                distribution: "series",                
              }
            ]
          }
        }     
    }
  },
  watch: {
    chartData: function(){
      this.updateChart()
    }
  },
  mounted() {
      this.updateChart()
    },
    methods: {
      applyFilter(value){
        this.chartData = this.chartData.slice(0, -value)
      },
      updateChart(){
        this.chartInfo.datasets[0].data = this.chartData
        this.renderChart(this.chartInfo, this.chartOptions)
      }
    }
}
</script>

<style lang="scss" scoped>
.graph-card{
  display: inline-block;
  width: 60%;
  position: relative;
  padding: 2%;
}
.graph{
  width: 95%;
}
.content-table{
  display: inline-block;
  width: 35%;
  margin-left: 2%;
  position: relative;
}
.btn-pos{
  position: relative;
}
</style>
