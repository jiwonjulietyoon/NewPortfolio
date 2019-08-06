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
                <div class="inner">

                </div>
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

export default {
  name: 'Contact',
  components: {
    NavArrows
  },
  data() {
    return {
      prev: "Projects",
    }
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
  height: 100px;
  border: 1px solid red;
  @include minWidth(601) {
    min-height: calc(94vh - 260px);
  }
  @include maxWidth(600) {
    
  }
}

.cardPreview {

}

.selectedCard {
  .outer {
    // width: 
  }
}


</style>
