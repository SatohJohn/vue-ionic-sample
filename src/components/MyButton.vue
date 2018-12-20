<template>
  <div>
    <ion-button shape="round" color="primary" fill="outline" @click="showModal">Show Modal</ion-button>
    <ion-input required type="text" @ionChange="change" placeholder="First Name"></ion-input>
  </div>
</template>

<script>
export default {
  name: 'MyButton',
  data() {
      return {
          message: ''
      }
  },
  methods: {
    async showModal() {
      // ボタンがクリックされたらionicのモーダルを表示
      const loading = await this.$ionic.loadingController.create({
        spinner: 'show',
        duration: 3000,
        message: this.message,
        translucent: true,
        cssClass: 'custom-class custom-loading'
      });
      loading.present();
    },
    change(e) {
      this.message = e.detail.value;
    }
  }
}
</script>