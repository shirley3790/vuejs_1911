<template>
  <!-- 科技组件 -->
  <div>
    <h1>体育实况</h1>
    <input type="text" />
    <button @click="add()">点我一下{{ num }}</button>
  </div>
</template>
<script>
export default {
  data: function() {
    return {
      num: 0
    };
  },
  methods: {
    add() {
      this.num++;
    }
  },
  created() {
    window.console.log("体育实况created了");
  },
  destroyed() {
    window.console.log("体育实况destroyed了");
  }
};
</script>