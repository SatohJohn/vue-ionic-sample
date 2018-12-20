<template>
  <section>
    <ion-list lines="full">
      <ion-item-sliding :key="person.id" v-for="person in persons">
        <ion-item>
          <ion-avatar slot="start">
            <img src="../assets/logo.png" />
          </ion-avatar>
          <ion-label>
            <h2>{{person.name}}</h2>
            <p>{{person.detail}}</p>
          </ion-label>
        </ion-item>
        <ion-item-options side="end">
          <ion-item-option @click="call(person)">call</ion-item-option>
        </ion-item-options>
      </ion-item-sliding>
    </ion-list>
    <ion-infinite-scroll threshold="100px" @ionInfinite="loadData">
      <ion-infinite-scroll-content
        loadingSpinner="bubbles"
        loadingText="Loading more data...">
      </ion-infinite-scroll-content>
    </ion-infinite-scroll>
  </section>
</template>

<script>
class Person{
  constructor(name, detail) {
    this.name = name;
    this.detail = detail;
    this.id = id++;
  }
}

let id = 0;

export default {
  name: 'MyList',
  data() {
    return {
      persons: [
        new Person("john", "i like Vue.js!"),
        new Person("bob", "i like Vue.js!"),
        new Person("alice", "i like Vue.js!"),
        new Person("mike", "i like Vue.js!"),
        new Person("john", "i like Vue.js!"),
        new Person("bob", "i like Vue.js!"),
        new Person("alice", "i like Vue.js!"),
        new Person("mike", "i like Vue.js!"),
        new Person("john", "i like Vue.js!"),
        new Person("bob", "i like Vue.js!"),
        new Person("alice", "i like Vue.js!"),
        new Person("mike", "i like Vue.js!"),
        new Person("john", "i like Vue.js!"),
        new Person("bob", "i like Vue.js!"),
        new Person("alice", "i like Vue.js!"),
        new Person("mike", "i like Vue.js!"),
        new Person("john", "i like Vue.js!"),
        new Person("bob", "i like Vue.js!"),
        new Person("alice", "i like Vue.js!"),
        new Person("mike", "i like Vue.js!")
      ]
    }
  },
  methods: {
    loadData(e) {
      window.console.log(e);
      this.persons.add(new Person("john", "i like Vue.js!"));
      this.persons.add(new Person("bob", "i like Vue.js!"));
      this.persons.add(new Person("alice", "i like Vue.js!"));
      this.persons.add(new Person("mike", "i like Vue.js!"));
    },
    async call(person) {
      const toast = await this.$ionic.toastController.create({
      message: `${person.name}`,
      duration: 2000
      });
      toast.present();
    }
  }
}
</script>