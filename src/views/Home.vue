<template>
  <section class="home">
    <p @click="toPage" style="font-size: 50px">去登录</p>
    <span style="display: inline-block;background-color: green;border-radius: 20px;width: 100px;height: 60px">ddd</span>
  </section>
</template>

<script>
  import { getNewList } from '../api/apiRoot'
  import Btn from '../components/Btn'

  export default {
    data () {
      return {}
    },
    created () {
      getNewList().then(res => {
        console.log(res)
      })
    },
    components: { Btn },
    methods: {
      toPage () {
        this.$store.dispatch('setUserInfo', 'jake101')
        this.$router.push({path: '/login',query: {id: 101, name: 'chen'}})
      }
    }
  }
</script>

<style scoped>
  .home{}
  .home p{font-size: 28px}
</style>
