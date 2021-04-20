<template>
  <div class="counter">
    <h1>Counter</h1>
    <p>{{ count }}</p>
    <div>
      <button
        class="btn btn-sm btn-primary"
        @click="increment"
      >+</button>
      <button
        class="ml-1 btn btn-sm btn-secondary"
        @click="decrement"
      >-</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0
    };
  },
  methods: {
    increment() {
      this.count++;
    },
    decrement() {
      this.count--;
    }
  }
};
</script>