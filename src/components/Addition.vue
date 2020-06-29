<template>
  <div>
    <h3>当前最新的count值为: {{ $store.state.count }}</h3>
    <!-- 使用getters显示 -->
    <h3>使用getters显示 {{ $store.getters.showNum }}</h3>

    <button @click="btnHandle1">+1</button>
    <button @click="btnHandle2">+N</button>
    <button @click="btnHandle3">+1 Async</button>
    <button @click="btnHandle4">+N Async</button>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  methods: {
    btnHandle1() {
      this.$store.commit('add')
    },
    btnHandle2() {
      this.$store.commit('addN', 3)
    },
    // 异步+1
    btnHandle3() {
      // 这里的dispatch函数专门用来触发action
      this.$store.dispatch('addAsync')
    },
    btnHandle4() {
      // 这里的dispatch函数专门用来触发action
      this.$store.dispatch('addNAsync', 4)
    }
  }
}
</script>
