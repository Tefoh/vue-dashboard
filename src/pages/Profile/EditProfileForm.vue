<template>
  <card>
    <template slot="header">
      <h5 class="title">ویرایش پروفایل</h5>
    </template>
    <div class="row">
      <div class="col-md-5 pr-md-1 text-right">
        <base-input label="سایت"
                    placeholder="سایت"
                    v-model="model.company"
                    disabled>
        </base-input>
      </div>
      <div class="col-md-3 px-md-1 text-right">
        <base-input label="نام کاربری"
                  placeholder="نام کاربری"
                  v-model="model.username">
        </base-input>
      </div>
      <div class="col-md-4 pl-md-1 text-right">
        <base-input label="ایمیل"
                  type="email"
                  placeholder="ایمیل">
        </base-input>
      </div>
    </div>

    <div class="row">
      <div class="col-md-6 pr-md-1 text-right">
        <base-input label="نام"
                  v-model="model.firstName"
                  placeholder="نام">
        </base-input>
      </div>
      <div class="col-md-6 pl-md-1 text-right">
        <base-input label="نام خانوادگی"
                  v-model="model.lastName"
                  placeholder="نام خانوادگی">
        </base-input>
      </div>
    </div>

    <div class="row">
      <div class="col-md-12 text-right">
        <base-input label="ادرس"
                  v-model="model.address"
                  placeholder="ادرس">
        </base-input>
      </div>
    </div>

    <div class="row">
      <div class="col-md-4 pr-md-1 text-right">
        <base-input label="شهر"
                  v-model="model.city"
                  placeholder="شهر">
        </base-input>
      </div>
      <div class="col-md-4 px-md-1 text-right">
        <base-input label="کشور"
                  v-model="model.country"
                  placeholder="کشور">
        </base-input>
      </div>
      <div class="col-md-4 pl-md-1 text-right">
        <base-input label="پلاک"
                  placeholder="پلاک">
        </base-input>
      </div>
    </div>
    <div class="row">
      <div class="col-md-8 text-right">
        <base-input>
          <label>درباره من</label>
          <textarea rows="4" cols="80"
                    class="form-control"
                    placeholder="بیشتر بدانید"
                    v-model="model.about">

              </textarea>
        </base-input>
      </div>
    </div>
    <template slot="footer">
      <base-button type="success" fill>ذخیره</base-button>
    </template>
  </card>
</template>
<script>
import {
  Card,
  BaseInput
} from "@/components/index";

import BaseButton from '@/components/BaseButton';

export default{
  components:{
    Card,
    BaseInput,
    BaseButton
  },
  props: {
    model: {
      type: Object,
      default: () => {
        return {};
      }
    }
  }

}
</script>
<style>

</style>
