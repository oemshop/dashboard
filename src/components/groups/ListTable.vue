<template lang="pug">
  table(cellspacing="0" cellpadding="0" width="100%").list-table
    thead
      tr
        th
          a(href='#')
            span #
            i.mdi.mdi-code-tags.mdi-rotate-90.order-icon
        th
          a(href='#')
            span CPF
            i.mdi.mdi-code-tags.mdi-rotate-90.order-icon
        th(width="100%")
          a(href='#')
            span Nome
            i.mdi.mdi-code-tags.mdi-rotate-90.order-icon
    tbody
      tr
        td 0000001
        td 12312312323
        td Juliano Bailão
      tr
        td 0000001
        td 12312312323
        td Juliano Bailão
      tr
        td 0000001
        td 12312312323
        td Juliano Bailão
</template>

<script>
export default {
  name: 'list-table',
  props: {
    columns: Array,
    rows: String
  }
}
</script>

<style lang="stylus">
  .list-table
    width calc(100%+1px)

    thead
      tr


        th
          color #fff
          font-weight normal
          text-shadow 1px 1px 1px rgba(255,255,255,.4)
          text-align left
          text-transform uppercase
          font-size 14px

          span
            padding 5px
            display inline-block

          .order-icon
            float right
            padding 5px

          a
            color #333
            display block
            text-decoration none
            transition all .25s ease
            background #ffee58
            outline 0
            box-shadow inset 1px 1px 0 rgba(255,255,255,.3),
              inset -1px -1px 0 rgba(0,0,0,.1)

            &:hover
              background #ffc107

            &:active
              box-shadow inset 2px 2px 0 rgba(0,0,0,.3),
                inset -2px -2px 0 rgba(255,255,255,.1)

    tbody
      tr
        background #fff

        &:nth-child(even)
          background #ededed

        td
          color #333
          padding 5px
          font-weight normal
          text-shadow 1px 1px 1px rgba(0,0,0,.1)
          text-align left
          text-transform uppercase
          font-size 14px
          transition all .25s ease
          box-shadow inset 1px 1px 0 rgba(255,255,255,.3),
            inset -1px -1px 0 rgba(0,0,0,.1),
            inset 0 5px 10px rgba(0,0,0,0)

        &:not(.search)
          cursor pointer

          &:hover
            background #ccc

          &:active
            background #bbb
            box-shadow inset 1px 1px 0 rgba(255,255,255,.3),
              inset -1px -1px 0 rgba(0,0,0,.1),
              inset 0 5px 10px rgba(0,0,0,.4)
</style>
