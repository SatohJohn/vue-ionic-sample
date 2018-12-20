<template>
  <div>
    <ion-button shape="round" color="primary" fill="outline" @click="showModal">Show Modal</ion-button>
    <ion-input required type="text" placeholder="First Name"></ion-input>
  </div>
</template>

<script>
export default {
  name: 'MyButton',
  methods: {
    async showModal() {
      // ボタンがクリックされたらionicのモーダルを表示
      const loading = await this.$ionic.loadingController.create({
        spinner: 'show',
        duration: 5000,
        message: 'Please wait...',
        translucent: true,
        cssClass: 'custom-class custom-loading'
      });
      loading.present();
    }
  }
}
</script>