<template>
  <div class="selectedCard">
    <div class="side left">
      <div class="jack">J</div>
      <img class="spade" src="~@/assets/spade.svg">
    </div>
    <div class="blackBorder">

    </div>
    <div class="side right">
      <div class="jack">J</div>
      <img class="spade" src="~@/assets/spade.svg">
    </div>
  </div>
</template>

<script>
export default {
  name: 'Intro',
  
}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";
@import "@/css/contactCards.scss";

.blackBorder {
  width: 72%;
  height: 82%;
  @include centerItem;
  border: 2px solid #181818;
  border-radius: 2px;
}
.side {
  width: 14%;
  height: 100%;
  position: absolute;
  top: 0;
  padding: 3% 0;
  &.left {
    left: 0;
  }
  &.right {
    right: 0;
    transform: rotate(180deg);
  }
  & > .jack {
    width: 100%;
    height: auto;
    text-align: center;
    font-family: $fontFancy;
    font-size: 2.5em;
  }
  & > .spade {
    transform: scaleX(0.75);
  }
}

</style>