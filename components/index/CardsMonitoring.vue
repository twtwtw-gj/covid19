<template>
  <cards-lazy-row :rows="rows" />
</template>

<script lang="ts">
/* eslint-disable simple-import-sort/imports -- ブラウザでの表示順に合わせて各 card の component を import する */
import Vue from 'vue'

import CardsLazyRow from '@/components/index/_shared/CardsLazyRow.vue'

// モニタリング項目
const MonitoringItemsOverviewCard = () =>
  import('@/components/index/CardsMonitoring/MonitoringItemsOverview/Card.vue')
// モニタリング項目(1)新規陽性者数
const MonitoringConfirmedCasesNumberCard = () =>
  import(
    '@/components/index/CardsMonitoring/MonitoringConfirmedCasesNumber/Card.vue'
  )
// モニタリング項目(2)#7119における発熱等相談件数
const ConsultationAboutFeverNumberCard = () =>
  import(
    '@/components/index/CardsMonitoring/ConsultationAboutFeverNumber/Card.vue'
  )
// モニタリング項目(3)新規陽性者における接触歴等不明者数
const UntrackedRateCard = () =>
  import('@/components/index/CardsMonitoring/UntrackedRate/Card.vue')
// モニタリング項目(4)検査の陽性率
const PositiveRateCard = () =>
  import('@/components/index/CardsMonitoring/PositiveRate/Card.vue')
// モニタリング項目(5)救急医療の東京ルールの適用件数
const TokyoRulesApplicationNumberCard = () =>
  import(
    '@/components/index/CardsMonitoring/TokyoRulesApplicationNumber/Card.vue'
  )
// モニタリング項目(6)入院患者数
const HospitalizedNumberCard = () =>
  import('@/components/index/CardsMonitoring/HospitalizedNumber/Card.vue')
// モニタリング項目(7)重症患者数
const SevereCaseCard = () =>
  import('@/components/index/CardsMonitoring/SevereCase/Card.vue')
/* eslint-enable simple-import-sort/imports */

export default Vue.extend({
  components: {
    CardsLazyRow,
  },
  data() {
    return {
      rows: [
        [MonitoringItemsOverviewCard, MonitoringConfirmedCasesNumberCard],
        [ConsultationAboutFeverNumberCard, UntrackedRateCard],
        [PositiveRateCard, TokyoRulesApplicationNumberCard],
        [HospitalizedNumberCard, SevereCaseCard],
      ],
    }
  },
})
</script>
