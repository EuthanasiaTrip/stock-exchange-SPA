<template>
<div class="page-field">
  <h1>Котировки</h1>
  <stocks-table
    :disablePagination="false"
    :hideFooter="false"
  ></stocks-table>
</div>
</template>

<script>
import StocksTable from "../components/StocksTable.vue"

export default {
  components: {
    StocksTable
  }
}
</script>

<style>
</style>

