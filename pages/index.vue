<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        div 何秒で反応できる？
        div ぬるぽスピード計測ツール
        div.headline ぬるぽメーター

        v-btn(to="/howtouse") 計測する

        div つくったひと : 
          a(href="https://twitter.com/hayate_inkling") HAYATE
</template>

<style>
.section {
  position: absolute;
  top: 0px;
  right: 0px;
  bottom: 0px;
  left: 0px;
  margin: auto;

  width: 100%;
  height: 50%;
}
</style>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  }
}
</script>
