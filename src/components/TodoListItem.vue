<template>
  <!-- todo プロパティのテキストを表示 -->
  <li>
    {{ todo.text }}
    <button @click="$emit('remove', todo.id)" class="btn btn-light btn-sm">x</button>
  </li>
</template>

<script>
export default {
  // 親コンポーネントから todo プロパティを受け取る
  props: {
    todo:{
      type: Object,
      required: true
    }
  }
};
</script>