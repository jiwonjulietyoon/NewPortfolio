<template>
  <section class="frameSection frameMiddle">
    <CastleTowerJ />
    <CastleTowerI />
    <CastleTowerW />
    <CastleTowerO />
    <CastleTowerN />
  </section>
</template>

<script>
import CastleTowerJ from '@/components/bookPage/castle/CastleTowerJ';
import CastleTowerI from '@/components/bookPage/castle/CastleTowerI';
import CastleTowerW from '@/components/bookPage/castle/CastleTowerW';
import CastleTowerO from '@/components/bookPage/castle/CastleTowerO';
import CastleTowerN from '@/components/bookPage/castle/CastleTowerN';

export default {
  name: "FrameMiddle",
  components: {
    CastleTowerJ,
    CastleTowerI,
    CastleTowerW,
    CastleTowerO,
    CastleTowerN
  }
}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";
@import "@/css/castle.scss";

</style>