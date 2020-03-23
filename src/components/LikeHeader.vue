<template>
  <div>
    <!-- <slot name="title" :user="user" text="text">デフォルトのタイトル</slot>
    <slot :user="user"></slot>
    <hr />
    <h2>トータルのいいね数</h2>
    <slot name="number"></slot>-->
    <slot></slot>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        firstName: 'Jack',
        lastName: 'Donald',
      },
    };
  },
};
</script>