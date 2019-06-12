<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        div.headline フライングしちゃダメだゾ！
        br
        v-btn(to="/howtouse") もう一度やり直す
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

.vs-sec {
  font-size: 15px;
}

.twitter-share-button {
  font-size: 30px;
}
</style>
