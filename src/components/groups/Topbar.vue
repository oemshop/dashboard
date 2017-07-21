<template lang="pug">
  header.topbar
    .menu
      a(href='#')
        i.mdi.mdi-menu
      a(href='#')
        i.mdi.mdi-bell
      a(href='#')
        i.mdi.mdi-compass
</template>

<script>
export default {
  name: 'topbar'
}
</script>

<style lang="stylus">
.topbar
  position relative
  z-index 2
  width 100%
  height 55px
  background #03a9f4

  &, .menu
    display flex
    flex-direction row
    align-items center
    justify-content flex-start

  .menu
    &.right
      margin-left auto

    a
      position relative
      display inline-block
      width 35px
      height 35px
      color #fff
      text-shadow 1px 1px 1px rgba(0,0,0,.2)
      font-size 21px
      border-radius 50%
      margin-left 10px
      transition all .25s ease
      outline none

      &:hover
        background rgba(0,0,0,.1)
        box-shadow inset 1px 1px 0 rgba(0,0,0,.1)

      &:active
        background rgba(0,0,0,.2)
        box-shadow inset 3px 3px 0 rgba(0,0,0,.2)

      i
        position absolute
        left 50%
        top 50%
        transform translate(-50%, -50%)
</style>
