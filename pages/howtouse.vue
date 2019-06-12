<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        div ぬるぽが見えたら
        v-img(src="/nurupo.jpg")
        div 下の「ガッ」ボタンを押そう！
        v-btn() ガッ！

        v-btn(to="/measure") ルールがわかったので計測をする
</template>

<style>
.section {
  position: absolute;
  top: 0px;
  right: 0px;
  bottom: 0px;
  left: 0px;
  margin: auto;

  width: 300px;
  height: 50%;
}
</style>
