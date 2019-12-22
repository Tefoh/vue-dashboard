<template>
  <div class="content">
    <div class="row">
      <div class="col-md-8">
        <edit-profile-form :model="model">
        </edit-profile-form>
      </div>
      <div class="col-md-4">
        <user-card :user="user"></user-card>
      </div>
    </div>
  </div>
</template>
<script>
import EditProfileForm from "./Profile/EditProfileForm.vue";
import UserCard from "./Profile/UserCard.vue";

export default{
  components:{
    EditProfileForm,
    UserCard
  },
  data() {
    return {
      model: {
        company: 'سایت وب آموز.',
        email: '@tefo_h',
        username: 'tefo',
        firstName: 'توفیق',
        lastName: 'حمزه ئی',
        address: 'ایران تهران',
        city: 'تهران',
        country: 'ایران',
        about: 'درباره من.'
      },
      user: {
        fullName: 'توفیق حمزه ئی',
        title: 'Ceo/Co-Founder',
        description: `از حقیقت نترسید زیرا ما باید در حقیقت بنیاد انسانی را مجدداً راه اندازی کنیم.`,
      }
    }
  }
}
</script>
<style>
</style>
