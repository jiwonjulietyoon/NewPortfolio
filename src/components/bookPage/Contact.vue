<template>
  <section class="bookPage">
    <div class="pageContainer">
      <h2 class="pageHeader">Contact</h2>

        <v-container class="vContainer">
          <v-layout row wrap>
            <!-- CARD PREVIEW -->
            <v-flex
              xs12 sm5
              class="cardPreview"
            >
              <div class="content">
                <div class="diamond">
                  <div class="trapezoid">
                    <div class="triUp"></div>
                  </div>
                  <div class="triDown">
                    <div class="triDown"></div>
                  </div>
                </div>
                <div class="cards" :style="cardsRotateStyle">
                  <div class="inner">
                    <div class="card intro" @click="rotateCards(0)">
                      <IntroPreview class="inner" />
                    </div>
                    <div class="card email" @click="rotateCards(-0.25)">
                      <EmailPreview class="inner" /> 
                    </div>
                    <div class="card git" @click="rotateCards(-0.5)">
                      <GitPreview class="inner" />
                    </div>
                    <div class="card linkedin" @click="rotateCards(0.25)">
                      <LinkedinPreview class="inner" />
                    </div>
                  </div>
                </div>
              </div>
            </v-flex>


            <!-- SELECTED CARD -->
            <v-flex
              xs12 sm7
              class="selectedCard"
            >
              <div class="outer">
                <Intro class="card intro" />
                <Email class="card email" />
                <Git class="card git" />
                <Linkedin class="card linkedin" />
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
import Intro from '@/components/bookPage/contactCards/Intro';
import IntroPreview from '@/components/bookPage/contactCards/IntroPreview';
import Email from '@/components/bookPage/contactCards/Email';
import EmailPreview from '@/components/bookPage/contactCards/EmailPreview';
import Git from '@/components/bookPage/contactCards/Git';
import GitPreview from '@/components/bookPage/contactCards/GitPreview';
import Linkedin from '@/components/bookPage/contactCards/Linkedin';
import LinkedinPreview from '@/components/bookPage/contactCards/LinkedinPreview';
import $ from 'jquery';

export default {
  name: 'Contact',
  components: {
    NavArrows,
    Intro,
    IntroPreview,
    Email,
    EmailPreview,
    Git,
    GitPreview,
    Linkedin,
    LinkedinPreview
  },
  data() {
    return {
      prev: "Projects",
      cardsRotateTurns: 0
    }
  },
  computed: {
    cardsRotateStyle() {
      return { transform: 'rotate(' + this.cardsRotateTurns + 'turn)'}
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
    },
    setCardPreviewSize() {
      let setSize = function() {
        let w = $('.cardPreview').width() - 20;
        let h = $('.cardPreview').height();
        let content = $('.cardPreview > .content');
        let cards = $('.cardPreview > .content > .cards');
        let W; let H;
        if ((w + 80) >= h) {
          W = h - 80;
          H = h;
        }
        else {
          W = w;
          H = w + 80;
        }
        content.css({
          'width': W,
          'height': H
        });
        cards.css({
          'width': W,
          'height': W
        })
      }
      setSize();
      $(window).resize(function() {
        setSize();
      });
    },
    rotateCards(turn) {
      this.cardsRotateTurns = turn;
    }
  },
  mounted() {
    this.setSelectedCardSize();
    this.setCardPreviewSize();
  }
}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";


///////////// CARD LAYOUT /////////////

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
  position: relative;
  & > .content {
    @include centerItem;
    // border: 1px solid cyan;
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





////////////// DIAMOND ///////////////

.diamond {
  margin: 0 auto;
  width: 60px; height: 60px;
  // border: 1px solid olive;
  @include maxWidth(600) {
    width: 40px; height: 40px;
    display: inline-block;
    transform: rotate(-90deg);
  }
  & > .trapezoid {
    // base <= width
    // height <= border-bottom
    // top width <= border-left, border-right;; larger border => narrower trapezoid top
    width: 60px;
    height: 0;
    border-bottom: 15px solid #00a2ff;
    border-left: 14px solid transparent;
    border-right: 14px solid transparent;
    @include maxWidth(600) {
      width: 40px;
      border-bottom-width: 10px;
      border-left-width: 10px;
      border-right-width: 10px;
    }
    margin: 0 auto;
    position: relative;
    & > .triUp {
      width: 0;
      height: 0;
      border-left: 17px solid transparent;
      border-right: 17px solid transparent;
      border-bottom: 15px solid #00C0FF;
      @include maxWidth(600) {
        border-left-width: 12px;
        border-right-width: 12px;
        border-bottom-width: 10px;
      }
      position: absolute;
      left: 50%;
      transform: translate(-50%);
    }
  }
  & > .triDown {
    // base <= border-left + border-right
    // height <= border-top
    width: 0;
    height: 0;
    border-left: 30px solid transparent;
    border-right: 30px solid transparent;
    border-top: 40px solid #00C0FF;
    @include maxWidth(600) {
      border-left-width: 20px;
      border-right-width: 20px;
      border-top-width: 27px;
    }
    margin: 0 auto;
    position: relative;
    & > .triDown {
      width: 0;
      height: 0;
      border-left: 17px solid transparent;
      border-right: 17px solid transparent;
      border-top: 40px solid #00A2FF;
      @include maxWidth(600) {
        border-left-width: 12px;
        border-right-width: 12px;
        border-top-width: 27px;
      }
      position: absolute;
      left: 50%;
      bottom: 100%;
      transform: translate(-50%);
    }
  }
}





////////////// PREVIEW CARDS ///////////////  

.cardPreview .cards {
  margin-top: 20px;
  // border: 1px solid hotpink;
  border-radius: 50%;
  position: relative;
  transition: all 0.5s;
  &:hover {
    .inner {transform: scale(1.01);}
    .card {box-shadow: 0px 0px 7px 0px #BBBBBB;}
  }
  .inner {
    width: 100%; 
    height: 100%; 
    position: relative;
    transition: all 0.3s;
  }
  .card {
    width: 22%;
    height: 31%;
    position: absolute;
    cursor: pointer;
    transition: all 0.3s;
    // border: 1px solid coral;
    &.intro {
      top: 0; left: 50%;
      transform: translate(-50%);
    }
    &.email {
      top: 35%; right: 5%;
      transform: rotate(90deg);
    }
    &.git {
      bottom: 0; left: 39%;
      transform: rotate(180deg);
    }
    &.linkedin {
      top: 35%; left: 5%;
      transform: rotate(-90deg);
    }
  }
}

////////////// SELECTED CARDS ///////////////  

// .selectedCard .outer 






</style>
