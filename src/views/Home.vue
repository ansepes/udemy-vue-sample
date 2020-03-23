<template>
  <div>
    <h3>Home</h3>
    <button @click="toUsers">Userのページへ</button>
    <p>{{ doubleCount }}</p>
    <button @click="increment(2)">+1</button>
    <button @click="decrement(2)">-1</button>
    <br />
    <input type="text" :value="message" @input="updateMessage" />
    <p>{{ message }}</p>
  </div>
</template>

<script>
import { mapGetters } from 'vuex';
// import { mapMutations } from 'vuex';
import { mapActions } from 'vuex';
export default {
  methods: {
    toUsers() {
      this.$router.push({
        name: 'users-id-profile',
        params: { id: 1 },
      });
    },
    // increment() {
    //   this.$store.commit('increment', 2);
    // },
    // decrement() {
    //   this.$store.commit('decrement', 2);
    // },
    // ...mapMutations(['increment', 'decrement']),

    // increment() {
    //   this.$store.dispatch('increment', 2);
    // },
    // decrement() {
    //   this.$store.dispatch('decrement', 2);
    // },
    ...mapActions('count', ['increment', 'decrement']),
    updateMessage(e) {
      this.$store.dispatch('updateMessage', e.target.value);
    },
  },
  computed: {
    ...mapGetters('count', ['doubleCount']),
    message() {
      return this.$store.getters.message;
    },
  },
};
</script>
