<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        h1 CountDown:
          vac(:end-time="new Date().getTime() + 4000")
            span(slot="process" slot-scope="{ timeObj }") {{ timeObj.s}}
            span(slot="finish") 計測中......

        v-img(v-if="isCounting" src="/nurupo_blank.png" width="300px" height="300px")
        v-img(v-if="!isCounting" src="/nurupo.jpg" width="300px" height="300px")

        v-btn(v-on:click="stopTimer()") ガッ！
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

<script>
export default {
  data() {
    return {
      count: 3,
      isCounting: true,
      isStop: false,
      startTime: Date.now(),
      endTime: Date.now()
    }
  },
  mounted() {
    var countDown = 4000
    var min = 2
    var max = 5
    var randCount = Math.floor( Math.random() * (max + 1 - min) ) + min
    var timeout = countDown + randCount*1000
    setTimeout(() => {
      this.isCounting = false
      this.startTime = Date.now()
    }, timeout)
  },
  methods: {
    stopTimer: function () {
      if (this.isCounting) {
        this.$router.push('/failure')
        return;
      }
      this.endTime = Date.now()
      this.isStop = true
      var visibleFrame =  (this.endTime - this.startTime)/15
      var visibleSec =  (this.endTime - this.startTime)/1000
      if (!this.$device.isDesktop) { 
        var errorFrame = 13
        visibleFrame -= errorFrame
        visibleSec -= errorFrame * 0.015
      }
      this.$router.push('/result?vf=' + visibleFrame + '&vs=' + visibleSec)
    }
  }
}
</script>
