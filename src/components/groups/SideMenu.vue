<template lang="pug">
  .sidemenu-item(v-bind:class="{'active': this.opened}")
    a(href='#' v-on:click="open()")
      span.icon
        i.mdi(v-bind:class="'mdi-' + icon")
      span.title {{ title }}
      i.mdi.mdi-chevron-down.chevron
    .submenu(:style="'max-height:' + submenuHeight")
      a(v-for="item in submenu" :key="item.id" :href="item.href") {{ item.title }}
</template>

<script>
export default {
  name: 'side-menu',
  props: {
    icon: String,
    title: String,
    submenu: Array
  },
  methods: {
    open: function () {
      this.opened = !this.opened
      this.submenuHeight = this.opened === false ? 0
        : (this.$el.querySelectorAll('.submenu a').length * 33) + 'px'
    }
  },
  data () {
    return {
      opened: false,
      submenuHeight: 0
    }
  }
}
</script>

<style lang="stylus">
.sidemenu-item
  & > a
    position relative
    display block
    color #fff
    text-decoration none
    border-bottom solid 1px rgba(0,0,0,.15)
    outline none
    transition all .25s ease

    .icon,
    .title
      display inline-block
      vertical-align middle

    .icon
      width 55px
      padding 10px 0
      font-size 22px
      text-align center
      background rgba(0,0,0,.15)

    .title
      margin-left 10px

    .chevron
      position absolute
      right 10px
      top 12px
      transition all .25s ease

    &:hover
      background rgba(0,0,0,.2)
      box-shadow inset 0 0 5px rgba(0,0,0,.2),
        inset 0 0 5px rgba(0,0,0,.4)

    &:active
      background rgba(0,0,0,.8)

    & + .submenu
      display block
      background rgba(0,0,0,.3)
      overflow hidden
      transition all .25s ease

      a
        display block
        color #fff
        padding 7px
        padding-left 15px
        text-decoration none
        border-bottom solid 1px rgba(255,255,255,.1)
        background rgba(0,0,0,0)
        transition all .25s ease
        outline none

        &:last-child
          border none

        &:hover
          background rgba(0,0,0,.5)
          box-shadow inset 0 0 5px rgba(0,0,0,.2), inset 0 0 5px rgba(0,0,0,.3)

        &:active
          background rgba(0,0,0,.8)
          box-shadow inset 0 0 5px rgba(0,0,0,.4), inset 0 0 5px rgba(0,0,0,.6)

  &.active
    & > a
      background rgba(0,0,0,.2)

      .chevron
        transform rotate(180deg)
</style>
