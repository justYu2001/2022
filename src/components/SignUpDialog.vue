<template>
  <ArrowDialog v-model="dialogStore.signUpDialogOpened">
    <h2 class="title">報名資訊</h2>
    <div class="content">
      <p class="text">
        SITCON 年會堅持不收費原則，秉持著「降低學生參與門檻」的理念，預算全數由個人／企業贊助或是政府／教育單位協助，若您也認同 SITCON 的理念，歡迎 <router-link to="/sponsor"  @click="dialogStore.signUpDialogOpened = false">支持我們</router-link>。<br><br>

        <ul>
          <li>學生 / 普通票 於 07/16（六）20:00 及 08/06（六）20:00 在 <a href="https://sitcon.kktix.cc/events/sitcon2022" target="_blank">KKTIX</a> 開放報名。</li>
          <li>透過開源貢獻，您也可以直接取得門票，修 code、發 issue 及舉辦開源推廣活動等均能申請，詳細規則請見 <a href="https://oscvpass.ocf.tw" target="_blank">OSCVPass</a> 網站，務必在 07/18（一）前送出申請表單。</li>
          <li>偏鄉、離島及海外學生於 7/10（日）前可申請「<a href="https://hackmd.io/@SITCON/rJjIFtkOq" target="_blank">遠道而來票</a>」，期許能提供偏鄉及離島地區學生接觸資訊領域的機會，也鼓勵國外的學生來台進行交流。</li>
        </ul>
      </p>
      <div class="btns">
        <btn href="https://sitcon.kktix.cc/events/sitcon2022">KKTIX 報名連結</btn>
        <btn href="https://oscvpass.ocf.tw">OSCVPass 申請</btn>
        <btn href="https://hackmd.io/@SITCON/rJjIFtkOq">遠道而來票</btn>
        <btn to="/sponsor" @click="dialogStore.signUpDialogOpened = false">
          <img class="cat-right" src="/imgs/cats/cat-right-angle.svg" />
          支持我們
        </btn>
      </div>
    </div>
    <cat-flat-vertical class="cat-flat" />
  </ArrowDialog>
</template>
<script>
import { useDialogStore } from '../store/dialog'
export default {
  setup() {
    const dialogStore = useDialogStore()
    return { dialogStore }
  },
}
</script>
<style lang="sass" scoped>
.content
  padding: 0 24px
  display: flex
  flex-direction: row
  @media screen and (max-width: 920px)
    flex-direction: column
    padding: 0
  .title
    margin: 0
  .btns
    white-space: nowrap
    padding: 16px 24px
    display: grid
    grid-template: repeat(2, 1fr) / repeat(2, 1fr)
    grid-gap: 40px 32px
    @media screen and (max-width: 512px)
      padding: 0 32px
      grid-template: repeat(3, 1fr) / 1fr
      grid-gap: 24px
    .btn
      position: relative
.cat-flat
  height: 40%
  max-width: 15%
  position: absolute
  bottom: 20%
  right: -4px
  @media screen and (max-width: 768px)
    bottom: 5%
    max-width: 10%
.cat-right
  position: absolute
  top: 0
  left: 0
  transform: translate(-35%, -30%)
  max-width: 50%
  max-height: 150%
</style>
