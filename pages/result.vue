<template lang="pug">
  v-layout(column justify-center align-center)
    v-flex(xs12 sm8 md6)
      div.text-xs-center.section
        div.headline あなたの反応速度は
        div.display-2 {{ vs }}秒!
        div.headline {{ showText(vs) }}

        a.twitter-share-button(
          href="https://twitter.com/share?ref_src=twsrc%5Etfw"
          data-show-count="true"
          :data-text="'あなたのぬるぽ反応速度は' + vs + '秒でした！' + showText(vs) + ' | #ぬるぽメーター'"
          data-size="large"
          data-lang="ja"
          data-url="http://bit.ly/2wQeUQl"
          ) ツイート
        span で結果をシェア
        script(async src="https://platform.twitter.com/widgets.js" charset="utf-8")
        br
        v-btn(to="/") トップに戻る
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

<script>
import BigNumber from 'bignumber.js'

export default {
  data() {
    var vf = new BigNumber(this.$route.query.vf).toFixed(0)
    var vs = new BigNumber(this.$route.query.vs).toFixed(2)
    return {
      vf: vf,
      vs: vs
    }
  },
  methods: {
    round: function (num, digit) {
      return new BigNumber(num).toFixed(digit)
    },
    showText: function (vs) {
      if (vs < 0) {
        return "時をかけるぬるぽです！未来から来ていませんか？";
      }
      if (vs < 0.1) {
        return "「ぬるぽ限界生物」です！人間の限界を超えています！";
      }
      if (vs < 0.13) {
        return "「ぬるぽ超人類」です！ウサインボルトと同じ反応速度です！";
      }
      if (vs < 0.14) {
        return "「ぬるぽの申し子」です！一流アスリートと同じくらいの反応速度です！";
      }
      if (vs < 0.15) {
        return "「ぬるぽオリンピック選手」です！出そうと思ってもなかなか出せません！";
      }
      if (vs < 0.15) {
        return "「ぬるーポッター」です！相当速い反射速度です！";
      }
      if (vs < 0.16) {
        return "「ぬるぽ５G」です！次世代のスピードです！";
      }
      if (vs < 0.17) {
        return "「ぬるポルシェ」です！平均よりもかなり速いです！";
      }
      if (vs < 0.18) {
        return "「ぬるぽインターハイ出場者」です！素材がいいですね！";
      }
      if (vs < 0.2) {
        return "「ハイパーぬるぽクリエイター」です！平均より速いです！";
      }
      if (vs < 0.21) {
        return "「ぬるポテンシャル」です！のびしろですねぇ！";
      }
      if (vs < 0.22) {
        return "「ぬるぽネクストエイジ」です！期待がかかる反応速度です！";
      }
      if (vs < 0.23) {
        return "「ぬるぽコンサルタント」です！平均以上です！";
      }
      if (vs < 0.24) {
        return "「ぬるぽインストラクター」です！平均を超えています！";
      }
      if (vs < 0.25) {
        return "「毛が生えたぬるぽ」です！平均よりわずかに速いです！！";
      }
      if (vs < 0.26) {
        return "「平均的なぬるぽ」です！";
      }
      if (vs < 0.3) {
        return "「ぬるぽ見習い」です！これからですよ！";
      }
      if (vs < 0.5) {
        return "「ぬるぽビギナー」です！もっと早くできるはず！";
      }
      if (vs < 1) {
        return "「生まれたてのぬるぽ」です！日々圧倒的成長！";
      }
      if (vs < 4) {
        return "「ぬるぽスロースターター」です！自分のペースは大事ですね！";
      }
      if (vs < 7) {
        return "「ぬるぽセラピスト」です！優しいですね！";
      }
      if (vs < 12) {
        return "「ぬるぽドクター」です！いつも叩かれるぬるぽが喜んでいます！";
      }
      if (vs < 13) {
        return "「ぬるぽ焼き土下座職人」です！がっ・・・！がっ・・・！がっ・・・！";
      }
      if (vs < 30) {
        return "「ぬるポエマーです！」のんびりするのもいいですね！";
      }
      if (vs < 60) {
        return "「ぬるぽツッコミ待ち芸人」です！遅すぎます！さてはわざとですね？";
      }
      if (vs < 120) {
        return "「ぬるぽ添い寝屋さん」です！遅すぎてぬるぽが隣で寝ていますよ！";
      }
      if (vs < 180) {
        return "「インスタントぬるぽ」です！待ってても何も起こりません！";
      }
      if (vs < 500) {
        return "「ぬるぽ修行僧」です！何と闘ってるのかは知りませんが、道のりは長いですよ！";
      }
      if (vs < 1000) {
        return "「ぬるぽの上にも3年」です！何かの修行ですか？";
      }
      if (999< vs) {
        return "「ぬるぽっくり」です！ 何かあったのかと思いました、、、";
      }
    }
  }
}
</script>
