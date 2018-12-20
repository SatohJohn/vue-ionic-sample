<template>
  <ion-tabs>
    <ion-tab label="Music" icon="musical-note" @click="showModal"></ion-tab>
    <ion-tab label="Profile" icon="person"></ion-tab>
    <ion-tab label="people" icon="people"></ion-tab>
  </ion-tabs>
</template>

<script>
export default {
  name: 'MyTab',
  methods: {
    async showModal() {
      const loading = await this.$ionic.loadingController.create({
        spinner: 'show',
        duration: 5000,
        message: 'Please wait...',
        translucent: true,
        cssClass: 'custom-class custom-loading'
      });
      loading.present();
    },
    async showToast() {
      const toast = await this.$ionic.toastController.create({
      message: 'Your settings have been saved.',
      duration: 2000
      });
      toast.present();
    }
  }
}
</script>