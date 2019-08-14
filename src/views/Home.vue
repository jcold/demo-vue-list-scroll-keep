<template>
  <div class="home"
       ref="box">
    <div id="box">
      <div class="item"
           v-for="i in dataList"
           :key="i"
           @click="handleClick">{{i}}</div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  },
  data() {
    return {
      dataList: []
    }
  },
  methods: {
    handleClick() {
      console.log('click fired', this.$refs.box.scrollTop)
      cur_pos_y = this.$refs.box.scrollTop
      this.$router.push({ name: 'about' })
    }
  },
  mounted() {
    console.log('home page mouted')

    setTimeout(() => {
      this.dataList = new Array(600).fill(null).map((x, i) => i)
      this.$nextTick(() => {
        this.$refs.box.scrollTo(0, cur_pos_y)
      })
    }, 1000)
  }
}
</script>
<style scoped>
.home {
  width: calc(100% - 50px);
  height: calc(100vh - 350px);
  overflow: auto;
}
.item {
  height: 30px;
  line-height: 30px;
  cursor: pointer;
  background-color: #eee;
}
</style>
