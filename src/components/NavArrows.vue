<template>
  <nav>
    <span id="navPrev" class="navBtn">
      <div class="navArrowRec"></div>
      <div class="navArrowTri"></div>
    </span>
    <span id="navNext" class="navBtn">
      <div class="navArrowRec"></div>
      <div class="navArrowTri"></div>
    </span>
  </nav>
</template>


<script>
export default {
  name: 'NavArrows',

}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";

nav {
  width: 100%;
  height: 50px;
  position: relative;
}
.navBtn {
  width: 32px;
  height: 32px;
  position: absolute;
  bottom: 10px;
  background-color: $navArrows;
  cursor: pointer;
  border-radius: 50%;
  &:hover {background-color: $navArrowsHover;}
  &:active {background-color: $bgBlack;}
  &.disabled {display: none;}
  &#navPrev {
    left: 15px;
  }
  &#navNext {
    right: 15px;
  }
}

.navArrowRec {
  position: absolute;
  width: 10px;
  height: 8px;
  top: 50%;
  transform: translate(-50%, -50%);
  background-color: white;
  #navPrev > & {left: 20px;}
  #navNext > & {right: 10px;}
}
.navArrowTri {
  position: absolute;
  width: 0;
  height: 0;
  top: 7.25px;
  left: 52%;
  border-top: 9px solid transparent;
  border-left: 10px solid white;
  border-bottom: 9px solid transparent;
  #navPrev > & {
    border-left: none;
    border-right: 10px solid white;
    left: 17%;
  }
}
</style>