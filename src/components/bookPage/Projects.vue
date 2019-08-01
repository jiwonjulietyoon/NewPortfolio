<template>
  <section class="bookPage">
    <div class="pageContainer">
      <h2 class="pageHeader">Projects</h2>
      <v-container>
        <v-layout row wrap>
          <v-flex
            v-for="p in projects"
            :key="p.id"
            xs12 sm6 md4 lg3
            class="projectFlex"
          >
            <div class="projectBox">

              <div class="btn-box">

              </div>
            </div>
          </v-flex>
        </v-layout>
      </v-container>
    </div>
    <NavArrows :prevLabel="prev" :prevName="prev" :nextLabel="next" :nextName="next"/>
  </section>
</template>


<script>
import NavArrows from '@/components/NavArrows';

export default {
  name: 'Project',
  components: {
    NavArrows
  },
  data() {
    return {
      prev: "Skills",
      next: "Contact",
      projects: [
        {
          id: 1,
          title: 'Movie Recommendation App',
          info: '[May 2019] Movie Recommendation Web Service (SPA) / Built on Django & Python via c9.io / Vue.js, Axios',
          more: 'https://drive.google.com/drive/folders/1nF4oy4G7vFhJsOuhYuLx8J7F-98qmicc?usp=sharing',
          git: 'https://github.com/ChangmoKang/PJT'
        },
        {
          id: 2,
          title: 'Sample 2',
          info: 'Then this will state that the font-size of the element should always be 100% of the height of the viewport at all times (50vh would be 50%, 15vh would be 15% and so on).',
          more: 'https://drive.google.com/drive/folders/1nF4oy4G7vFhJsOuhYuLx8J7F-98qmicc?usp=sharing',
          git: 'https://github.com/ChangmoKang/PJT'
        },
        {
          id: 3,
          title: 'Sample 3',
          info: 'In the demo below try resizing the height of the example to watch the type stretch:',
          more: 'https://drive.google.com/drive/folders/1nF4oy4G7vFhJsOuhYuLx8J7F-98qmicc?usp=sharing',
          git: 'https://github.com/ChangmoKang/PJT'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";

</style>