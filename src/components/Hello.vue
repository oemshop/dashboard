<template lang="pug">
  .hello
    title-bar(title="Registros encontrados" :breadcrumbs="[{href: '#', title:'Pessoas'}]")
      v-button(icon="plus" title="Incluir Novo")
    .negative-wrapper
      .card
        .card-body
          list-table
        .card-footer.no-border
          h2.title Mostrando do 01 ao 20 de 200 regisros
          .right
            .pagination
              a(href="#")
                i.mdi.mdi-chevron-double-left
              a(href="#")
                i.mdi.mdi-chevron-left
              a(href="#") Página 1
              a(href="#")
                i.mdi.mdi-chevron-right
              a(href="#")
                i.mdi.mdi-chevron-double-right
</template>

<script>
import TitleBar from '@/components/groups/TitleBar.vue'
import ListTable from '@/components/groups/ListTable.vue'
import VButton from '@/components/common/VButton.vue'

export default {
  name: 'hello',
  components: {
    TitleBar,
    ListTable,
    VButton
  }
}
</script>

<style lang="stylus">
  .negative-wrapper
    position relative
    z-index 3
    margin -50px 20px 0 20px

  .pagination
    display flex
    flex-direction row
    align-items center
    justify-content flex-start

    a
      color #fff
      background #263238
      font-size 13px
      text-decoration none
      padding 7px
      text-transform uppercase
      box-shadow inset 0 0 10px rgba(0,0,0,0)
      outline 0
      transition all .25s ease

      &:hover
        background #37474f

      &:active
        box-shadow inset 0 0 10px rgba(0,0,0,.9)

  .card
    background #fff
    overflow hidden
    border-radius 2px
    box-shadow: 0 3px 6px rgba(0,0,0,0.16),
      0 3px 6px rgba(0,0,0,0.23)

    .card-header,
    .card-body,
    .card-footer
      display flex
      flex-direction row
      align-items center
      justify-content flex-start

      .right
        margin-left auto

    .card-body
      padding 10px
      align-items flex-start
      height calc(100vh - 210px)

    .card-footer
      padding 10px
      background #263238
      color rgba(255,255,255,.8)

    .card-header
      padding 10px

      & +.card-body
        height calc(100vh - 245px)

    .title
      margin 0
      padding 0
      font-weight normal
      font-size 14px
</style>
