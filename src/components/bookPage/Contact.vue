<template>
  <section class="bookPage">
    <div class="pageContainer">
      <h2 class="pageHeader">Contact</h2>

        <v-container class="vContainer">
          <v-layout row wrap>
            <v-flex
              xs12 sm5
              class="cardPreview"
            >

            </v-flex>
            <v-flex
              xs12 sm7
              class="selectedCard"
            >
              <div class="outer">

              </div>
            </v-flex>
          </v-layout>
        </v-container>


    </div>
    <NavArrows :prevLabel="prev" :prevName="prev" :nextActive="false" />
  </section>
</template>


<script>
import NavArrows from '@/components/NavArrows';
import $ from 'jquery';

export default {
  name: 'Contact',
  components: {
    NavArrows
  },
  data() {
    return {
      prev: "Projects",
    }
  },
  methods: {
    setSelectedCardSize() {
      let setSize = function() {
        let w = $('.selectedCard').width();
        let h = $('.selectedCard').height();
        let selOuter = $('.selectedCard > .outer');
        let W; let H;
        if ((w-20) * 1.4 >= h) {
          W = h / 1.4;
          H = h;
        }
        else {
          W = w - 20;
          H = W * 1.4
        }
        selOuter.css({
          'width': W,
          'height': H
        });
      }
      setSize();
      $(window).resize(function() {
        setSize();
      });
    }
  },
  mounted() {
    this.setSelectedCardSize();
  }
}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";

.vContainer {
  padding-top: 0;
  margin: 0 auto;
  max-width: 1264px;
  @include maxWidth(1264) {
    max-width: 960px;
  }
}

.cardPreview, .selectedCard {
  border: 1px solid red;
  @include minWidth(601) {
    min-height: calc(94vh - 260px);
  }
}

.cardPreview {
  @include maxWidth(600) {
    min-height: 150px;
  }
}

.selectedCard {
  @include maxWidth(600) {
    min-height: 200px;
  }
  position: relative;
  .outer {
    margin: 0 auto;
    @include centerItem;
    border-radius: 5px;
    border: 1px solid blue;
  }
}


</style>
