<template>
  <div class="content">
    <div class="row">
      <div class="col-12">
        <card>
          <template slot="header">
            <h4 class="card-title">جدول ساده</h4>
          </template>
          <div class="table-responsive text-right">
            <base-table :data="table1.data"
                        :columns="table1.columns"
                        thead-classes="text-primary">
            </base-table>
          </div>
        </card>
      </div>

      <div class="col-12">
        <card class="card-plain">
          <template slot="header">
                <h4 class="card-title"> جدول با پیش زمینه ساده</h4>
                <p class="category"> اینم از تیتر جدول</p>
              </template>
          <div class="table-full-width table-responsive text-right">
            <base-table :title="table2.title" :sub-title="table2.subTitle" :data="table2.data"
                        :columns="table2.columns">
            </base-table>
          </div>
        </card>
      </div>

    </div>
  </div>
</template>
<script>

import {
  Card
} from "@/components/index";

import BaseTable from "@/components/BaseTable";

const tableColumns = ["نام", "کشور", "شهر", "درامد"];
const tableData = [
  {
      "id": 1,
      "نام": "توفیق حمزه ئی",
      "درامد": "465144",
      "کشور": "ایران",
      "شهر": "تهران"
  },
  {
      "id": 2,
      "نام": "محمد نیکو",
      "درامد": "$23,789",
      "کشور": "ایران",
      "شهر": "تهران"
  },
  {
      "id": 3,
      "نام": "صیاد اعظمی",
      "درامد": "$56,142",
      "کشور": "ایران",
      "شهر": "تهران"
  },
  {
      "id": 4,
      "نام": "محمد محمدی",
      "درامد": "$38,735",
      "کشور": "ایران",
      "شهر": "تهران"
  },
  {
      "id": 5,
      "نام": "احمد احمدی",
      "درامد": "$63,542",
      "کشور": "ایران",
      "شهر": "تهران"
  }
];


export default{
  components:{
    Card,
    BaseTable
  },
  data() {
    return {
      table1: {
        title: "Simple Table",
        columns: [...tableColumns],
        data: [...tableData]
      },
      table2: {
        title: "Table on Plain Background",
        columns: [...tableColumns],
        data: [...tableData]
      }
    };
  }
}
</script>
<style>
</style>
