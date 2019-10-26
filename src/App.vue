<template>
  <div id="app">
    <Invoice/>
<!--    <Table></Table>-->
  </div>
</template>

<script>
import Invoice from './components/Invoice'
import Table from './components/childComponents/Table'

export default {
  name: 'app',
  components: {
    Invoice,
    Table
  }
}
</script>

<style>
@import "./assets/css/normalize.css";
</style>
