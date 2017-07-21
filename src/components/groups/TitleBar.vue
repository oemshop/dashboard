<template lang="pug">
  .title-bar
    .left-data
      .breadcrumbs
        a(href="#")
          i.mdi.mdi-home
        a(v-for="item in breadcrumbs" :href="item.href") {{ item.title }}
      h1.title {{ title }}
    .right-data
      slot
</template>

<script>
export default {
  name: 'title-bar',
  props: {
    breadcrumbs: Array,
    title: String
  }
}
</script>

<style lang="stylus">
  .title-bar
    position relative
    background #03a9f4
    background-size 100vw
    box-shadow 0 3px 6px rgba(0,0,0,0.15)
    display flex
    flex-direction row
    align-items center
    justify-content flex-start
    padding 0 20px 60px
    box-sizing border-box

    .left-data,
    .right-data
      position relative
      z-index 2

    .left-data
      display flex
      flex-direction column
      align-items flex-start
      justify-content center

    .right-data
      margin-left auto

    .breadcrumbs
      a
        color #eee
        font-size 12px
        text-transform uppercase
        text-decoration none
        display inline-block
        vertical-align middle
        text-shadow 1px 1px 1px rgba(0,0,0,.2)
        transition all .25s ease

        &:after
          content "\F142"
          display inline-block
          vertical-align middle
          font normal normal normal 24px/1 "Material Design Icons"
          font-size inherit
          text-rendering auto
          line-height inherit
          -webkit-font-smoothing antialiased
          -moz-osx-font-smoothing grayscale

        &:last-child:after
          display none

        &:hover
          color #fff
          text-decoration underline

    .title
      color #fff
      font-weight normal
      margin 5px 0 0
</style>
