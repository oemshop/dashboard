<template lang="pug">
  #app
    sidebar
    main
      topbar
      .main-content
        router-view
</template>

<script>
import Sidebar from '@/components/groups/Sidebar.vue'
import Topbar from '@/components/groups/Topbar.vue'

export default {
  name: 'app',
  components: {
    Sidebar,
    Topbar
  }
}
</script>

<style lang="stylus">
@import url('https://fonts.googleapis.com/css?family=Roboto')

#app
  display flex
  flex-direction row
  flex-wrap no-wrap
  align-items flex-start
  justify-conten flex-start
  font-family 'Roboto', sans-serif
  font-size 15px

  main
    width 100%
    position relative
    z-index 1

    .main-content
      width 100%
      height calc(100vh - 55px)
      overflow hidden
      background #e0e0e0
</style>
