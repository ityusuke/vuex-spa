<template>
  <div class="sandbox">
    <!-- ここにこのコンポーネントの HTML を書きます -->
    <h1 @click="logger(msg)">SandBox</h1>
    <p>Computed reversed message: "{{ reversedMessage }}"</p>
    <p>{{ msg }}</p>
    <p>{{ now() }}</p>
    <input v-model.lazy="msg" placeholder="edit me">
    <p>Message is: {{ msg }}</p>
    <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
    <label for="jack">Jack</label>
    <input type="checkbox" id="john" value="John" v-model="checkedNames">
    <label for="john">John</label>
    <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
    <label for="mike">Mike</label>
    <br>
    <span>Checked names: {{ checkedNames }}</span>
  </div>
</template>

<script>
// ここに JavaScript を書きます

// このコンポーネントで使用する Vue オブジェクト
export default {
  // データ
  data() {
    return {
      msg: "Hello, World!",
      checkedNames: [],
    };
  },
  computed: {
    reversedMessage: function() {
      // `this` は vm インスタンスを指します
      return this.msg
        .split("")
        .reverse()
        .join("");
    }
  },
  // メソッド
  methods: {
    now() {
      return new Date();
    },
    logger(e){
      alert(e);
    }
  }
};
</script>

<style>
/* ここに、このコンポーネントに適用する CSS を書きます */
.sandbox {
  color: red;
}
</style>