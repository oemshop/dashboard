<template lang="pug">
  a.button(href='#')
    i.mdi(v-bind:class="'mdi-' + icon")
    span {{ title }}
</template>

<script>
export default {
  name: 'hello',
  props: ['icon', 'title']
}
</script>

<style lang="stylus">
  .button
    display flex
    flex-direction row
    align-items center
    justify-content flex-start
    color #fff
    padding 7px 15px
    border-radius 2px
    text-decoration none
    outline 0 !important
    text-shadow 1px 1px 1px rgba(0,0,0,.5)
    background linear-gradient(#76ff03, #64dd17)
    transition all .25s ease
    box-shadow 0 2px 0 rgba(0,0,0,.5),
      0 2px 6px rgba(0,0,0,.5),
      inset 0 2px 5px rgba(255,255,255,.2),
      inset 0 0 8px rgba(0,0,0,0)

    i
      font-size 22px

    span
      margin-left 10px

    &:hover
      box-shadow 0 2px 0 rgba(0,0,0,.8),
        0 2px 6px rgba(0,0,0,.9),
        inset 0 2px 5px rgba(255,255,255,.3),
        inset 0 0 8px rgba(255,255,255,.8)

    &:active
      box-shadow 0 2px 0 rgba(0,0,0,.8),
        0 2px 6px rgba(0,0,0,.9),
        inset 0 2px 5px rgba(255,255,255,.3),
        inset 3px 3px 8px rgba(0,0,0,.5)
</style>
