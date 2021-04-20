<template>
  
  <form @submit.prevent="$emit('add',text)">
    <input type="text" v-model="text" class="form-control"/>
    <input type="submit" value="作成">
  </form>
</template>


<script>
export default {
  // 親コンポーネントから todo プロパティを受け取る
  data() {
    return {
      text: ""
    };
  },
};
</script>