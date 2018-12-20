<template>
  <section>
    <ion-item>
      <ion-label>compoennt</ion-label>
      <ion-select :value="example" @ionChange="hoge" ok-text="OK" cancel-text="Dismiss">
        <ion-select-option value="MyList">リスト表示機能</ion-select-option>
        <ion-select-option value="MyButton">ボタン表示機能</ion-select-option>
        <ion-select-option value="MySlide">スライド表示機能</ion-select-option>
        <ion-select-option value="MyTab">タブ表示機能</ion-select-option>
      </ion-select>
    </ion-item>
    <div :is="example"></div>
  </section>
</template>

<script>
import MyButton from './components/MyButton.vue';
import MyList from './components/MyList.vue';
import MySlide from './components/MySlide.vue';
import MyTab from './components/MyTab.vue';

export default {
  name: 'app',
  data() {
    return {
      example: 'MyList',
      id: 0
    }
  },
  methods: {
    hoge(e) {
      window.console.log(e);
      this.example = e.detail.value;
    }
  },
  created() {

  },
  components: {
    MyButton,
    MyList,
    MySlide,
    MyTab
  }
}
</script>

<style>
</style>
