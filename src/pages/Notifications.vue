<template>
  <div class="content">
    <div class="row">
      <div class="col-md-6">
        <card>
          <template slot="header">
            <h4>استایل اطلاعیه ها</h4>
          </template>
          <base-alert type="info">
            <span>یک اطلاعیه ساده</span>
          </base-alert>
          <base-alert type="info" dismissible>
            <span>یک اطلاعیه ساده</span>
          </base-alert>
          <base-alert type="info" dismissible with-icon>
            <span data-notify="icon" class="tim-icons icon-bell-55"></span>
            <span data-notify="message">یک اطلاعیه با دکمه و ایکون.</span>
          </base-alert>
          <base-alert type="info" dismissible with-icon>
            <span data-notify="icon" class="tim-icons icon-bell-55"></span>
            <span data-notify="message">
              این یک اعلان با نزدیک است
               دکمه و ایکون و خطوط بسیاری دارد.
               می توانید ببینید که ایکون و نزدیک است
               دکمه همیشه به صورت عمودی تراز شده اند.
               این یک اعلان زیبا است.
               بنابراین لازم نیست نگران استایل باشید.
            </span>
          </base-alert>
        </card>
      </div>
      <div class="col-md-6">
        <card>
          <h4 slot="header">انواع اطلاعیه</h4>
          <base-alert type="primary" dismissible>
            <span><b> Primary - </b> یک اطلاعیه معمولی با کلاس ".alert-primary"</span>
          </base-alert>
          <base-alert type="info" dismissible>
            <span><b> Info - </b> یک اطلاعیه معمولی با کلاس ".alert-info"</span>
          </base-alert>
          <base-alert type="success" dismissible>
            <span><b> Success - </b> یک اطلاعیه معمولی با کلاس ".alert-success"</span>
          </base-alert>
          <base-alert type="warning" dismissible>
            <span><b> Warning - </b> یک اطلاعیه معمولی با کلاس ".alert-warning"</span>
          </base-alert>
          <base-alert type="danger" dismissible>
            <span><b> Danger - </b> یک اطلاعیه معمولی با کلاس ".alert-danger"</span>
          </base-alert>
        </card>
      </div>
      <div class="col-md-12">
        <card>
          <div class="row">
            <div class="col-md-6 ml-auto mr-auto text-center">
              <h4 class="card-title">
                محل های اطلاعیه ها
                <p class="category">کلیک کنین تا ببینید</p>
              </h4>
            </div>
          </div>
          <div class="row">
            <div class="col-lg-8 ml-auto mr-auto">
              <div class="row">
                <div class="col-md-4">
                  <base-button type="primary" block @click="notifyVue('top', 'left')">بالا چپ</base-button>
                </div>
                <div class="col-md-4">
                  <base-button type="primary" block @click="notifyVue('top', 'center')">بالا وسط</base-button>
                </div>
                <div class="col-md-4">
                  <base-button type="primary" block @click="notifyVue('top', 'right')">بالا راست</base-button>
                </div>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col-lg-8 ml-auto mr-auto">
              <div class="row">
                <div class="col-md-4">
                  <base-button type="primary" block @click="notifyVue('bottom', 'left')">پایین چپ</base-button>
                </div>
                <div class="col-md-4">
                  <base-button type="primary" block @click="notifyVue('bottom', 'center')">پایین وسط</base-button>
                </div>
                <div class="col-md-4">
                  <base-button type="primary" block @click="notifyVue('bottom', 'right')">پایین راست</base-button>
                </div>
              </div>
            </div>
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

import BaseAlert from '@/components/BaseAlert';
import BaseButton from '@/components/BaseButton';
import NotificationTemplate from './Notifications/NotificationTemplate';


export default{
  components:{
    BaseAlert,
    BaseButton,
    Card
  },
  data(){
    return {
      type:["","info","success","warning","danger"],
      notifications:{
        topCenter: false
      }
    };
  },
  methods:{
    notifyVue(verticalAlign, horizontalAlign){
      const color = Math.floor(Math.random() * 4 + 1);
      this.$notify({
        component: NotificationTemplate,
        icon: "tim-icons icon-bell-55",
        horizontalAlign: horizontalAlign,
        verticalAlign: verticalAlign,
        type: this.type[color],
        timeout: 0
      });
    }
  }
}
</script>
<style>
</style>
