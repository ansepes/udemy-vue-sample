<template>
  <div>
    <h3>Home</h3>
    <button @click="toUsers">Userのページへ</button>
    <p>{{ doubleCount }}</p>
    <button @click="increment(2)">+1</button>
    <button @click="decrement(2)">-1</button>
  </div>
</template>

<script>
import { mapGetters } from 'vuex';
import { mapMutations } from 'vuex';
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
    ...mapMutations(['increment', 'decrement']),
  },
  computed: {
    ...mapGetters(['doubleCount']),
  },
};
</script>
