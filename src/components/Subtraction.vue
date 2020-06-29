<template>
  <div>
    <!-- 第三步，直接使用 -->
    <h3>当前最新的count值为: {{ count }}</h3>
    <!-- 使用getters显示 -->
    <h3>使用getters显示 {{ showNum }}</h3>

    <button @click="btnHandle1">-1</button>
    <button @click="btnHandle2">-N</button>
    <button @click="subAsync">-1 Async</button>
    <button @click="subNAsync(6)">-N Async</button>
  </div>
</template>

<script>
// 第一步，导入
import { mapState, mapMutations, mapActions, mapGetters } from 'vuex'

export default {
  data() {
    return {}
  },
  // 第二步，声明为 computed & methods
  computed: {
    ...mapState(['count']),
    ...mapGetters(['showNum'])
  },
  methods: {
    ...mapMutations(['sub', 'subN']),
    ...mapActions(['subAsync', 'subNAsync']),

    btnHandle1() {
      this.sub()
    },
    btnHandle2() {
      this.subN(3)
    }
    // btnHandle3() {
    //   this.subAsync()
    // },
    // btnHandle4() {
    //   this.subNAsync(6)
    // }
  }
}
</script>
