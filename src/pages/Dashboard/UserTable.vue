<template>
  <base-table
              :data="table.data"
              :columns="table.columns"
              table-class="text-right"
              thead-classes="text-primary text-right">
  </base-table>

</template>
<script>

 import BaseTable from '@/components/BaseTable';

 export default{
   components: {
     BaseTable
   },
   computed: {
     table() {
       return this.$t('dashboard.usersTable');
     }
   }
 }

</script>
<style>
</style>
