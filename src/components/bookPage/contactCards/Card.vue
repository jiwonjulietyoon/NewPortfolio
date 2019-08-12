<template>
  <div class="selectedCard">
    <div class="side left">
      <div class="letter">{{text.letter}}</div>
      <img class="suit" :src="require(`@/assets/contact/suit_${text.suit}.svg`)">
    </div>
    <div class="side right">
      <div class="letter">{{text.letter}}</div>
      <img class="suit" :src="require(`@/assets/contact/suit_${text.suit}.svg`)">
    </div>
    <div class="blackBorder"></div>
    <div class="fadeBg"></div>
    <div class="main">

    </div>



    <!-- <div class="grungeBorder">
      <div class="top">
        <div class="text">{{text.top}}</div>
      </div>
      <div class="middle">
        <div class="address">
          <div class="text2" id="address">{{text.address}}</div>
        </div>
        <div class="copy">
          <div class="icon" @click="copyText" @mouseout="tooltipReset">
            <i class="material-icons-round">flag</i>
            <span class="tooltip" id="tooltip">Click to copy</span>
          </div>
        </div>
      </div>
      <div class="bottom">
        <div class="text">{{text.bottom}}</div>
      </div>
    </div> -->
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    text: {type: Object}
  },
  data() {
    return {

    }
  },
  methods: {
    copyText() {
      const $temp = $("<input>");
      $("body").append($temp);
      $temp.val($('#address').text().replace(/ /g,'')).select();
      document.execCommand("copy");
      $temp.remove();

      const tooltip = document.getElementById("tooltip");
      tooltip.innerHTML = "Copied to clipboard";
    },
    tooltipReset() {
      const tooltip = document.getElementById("tooltip");
      tooltip.innerHTML = "Click to copy";
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";
@import "@/css/contactCards.scss";
</style>

