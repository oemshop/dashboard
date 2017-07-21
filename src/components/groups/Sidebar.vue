<template lang="pug">
  aside.sidebar
    .header
      .logo
        i.mdi.mdi-chemical-weapon
        span Hub
    .menu-wrapper
      side-menu(v-for="item in menu" :icon="item.icon" :title="item.title" :submenu="item.submenu" :key="item.id")
</template>

<script>
import SideMenu from '@/components/groups/SideMenu.vue'

export default {
  name: 'sidebar',
  components: {
    SideMenu
  },
  data () {
    return {
      menu: [
        {
          icon: 'database',
          title: 'Cadastros',
          submenu: [
            {
              href: '#',
              title: 'Pessoas'
            }
          ]
        }
      ]
    }
  }
}
</script>

<style lang="stylus">
.sidebar
  position relative
  z-index 2
  width 320px
  height 100vh
  background #263238
  box-shadow 3px 0 6px rgba(0,0,0,0.23)

  .header
    height 55px
    position relative
    background #03a9f4

    .logo
      color #fff
      font-size 18px
      text-shadow 1px 1px 1px rgba(0,0,0,.4)

      i, span
        display inline-block
        vertical-align middle

      i
        position relative
        width 55px
        height 55px
        font-size 32px
        background rgba(0,0,0,.05)

        &:before
          position absolute
          left 50%
          top 50%
          transform translate(-50%, -50%)

      span
        margin-left 10px

  .menu-wrapper
    width 100%
    height calc(100vh - 55px - 138px)
    overflow auto
</style>
