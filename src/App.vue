<template>
  <div class="app">
    <section-large-banner/>
    <section-step-banner/>
    <!-- <popup-prizes v-if="popup-prizes.status" /> -->
    <!-- <popup-prizes/> -->
  </div>
</template>

<script> 
  import SectionLargeBanner from "@/components/SectionLargeBanner";
  import SectionStepBanner from "@/components/SectionStepBanner";
  import PopupPrizes from "@/components/PopupPrizes";
export default {
    components: {
      SectionLargeBanner, SectionStepBanner, PopupPrizes
    },
  data() {
    
  },
};
</script>

<style lang="scss">
@import './assets/scss/index.scss'; 

*{
  margin: 0;
  padding: 0;
  font-size: 10px;
}
section{
  background-color: #E7F5FF;
}

.btn {
    border-radius: 80px;
    background: #00bfff;
    @include adaptiv-font(24, 18);
  }
</style>
