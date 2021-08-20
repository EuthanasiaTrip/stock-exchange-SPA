<template>
<div>
  <v-card class="px-3 py-5 table-card"
  >
  <v-data-table
    class="table"
    :headers="headers"
    :items="tableData"
    :height="cardHeight"
    :disable-pagination="disablePagination"
    :hide-default-footer="hideFooter"     
    :footer-props="{
      disableItemsPerPage: true,
      itemsPerPageAllText: null,
      itemsPerPageOptions: []
      }"    
  >
  </v-data-table>
  </v-card>
</div>
</template>

<script>
export default {
  name: "StocksTable",
  props: {
    cardHeight: Number,
    disablePagination: {
      type: Boolean,
      default: false
    },
    hideFooter: {
      type: Boolean,
      default: true
    }
  },
  data(){
    return {
      headers: [{
        text: "Компания",
        value: 'company'
      },
      {
        text: "Тикер",
        value: "ticker"
      },
      {
        text: "Цена",
        value: "price"
      },
      {
        text: "Дата",
        value: "date"
      }],
      tableData: [{
        company: "АК АЛРОСА",
        ticker: "ALRS",
        price: "91,94"
      },
      {
        company: "Аэрофлот",
        ticker: "AFLT",
        price: "71,82"
      },
      {
        company: "Газпром",
        ticker: "GAZP",
        price: "193,30"
      },
      {
        company: "4",
        ticker: "GAZP",
        price: "193,30"
      },
      {
        company: "5",
        ticker: "GAZP",
        price: "193,30"
      },
      {
        company: "6",
        ticker: "GAZP",
        price: "193,30"
      },
      {
        company: "7",
        ticker: "GAZP",
        price: "193,30"
      },
      {
        company: "8",
        ticker: "GAZP",
        price: "193,30"
      },
      {
        company: "9",
        ticker: "GAZP",
        price: "193,30"
      },
      {
        company: "10",
        ticker: "GAZP",
        price: "193,30"
      },
      {
        company: "11",
        ticker: "GAZP",
        price: "193,30"
      },
      {
        company: "12",
        ticker: "GAZP",
        price: "193,30"
      },
      {
        company: "13",
        ticker: "GAZP",
        price: "193,30"
      },
      {
        company: "14",
        ticker: "GAZP",
        price: "193,30"
      }]
    }
  },
  methods: {
    checkProps(){
      console.log(this.cardHeight)
    }
  },
  created() {
    this.checkProps()
  }
}
</script>

<style>
.table-card {
  width: 100%;
  position: relative;
  top: 15px;
}
.table {
  padding: auto;
  width: 98%;
  position: relative;
  left: 1%;
}
</style>