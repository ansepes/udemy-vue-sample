<template>
  <div>
    <h2>{{ title | lowerCase | upperCase }}</h2>
    <p>{{ subTitle | upperCase }}</p>
    <p>{{ number }}</p>
    <button @click="number += 1">+1</button>
  </div>
</template>

<script>
import { tokyoNumber } from '@/mixins/tokyoNumber';

export default {
  mixins: [tokyoNumber],
};
</script>
