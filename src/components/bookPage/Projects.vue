<template>
  <section class="bookPage">
    <div class="pageContainer">
      <h2 class="pageHeader">Projects</h2>
      <v-container>
        <v-layout row wrap class="projectRow">
          <v-flex
            v-for="p in projects"
            :key="p.id"
            xs12 sm6 md4 lg3
            class="projectFlex"
          >
            <div class="projectBox">
              <img :src="p.img" alt="Project Overview">
              <div class="projectInfo">
                <div class="details">

                </div>
                <div class="btn-box">
                  <button class="btn">View More</button>
                  <button class="btn">View Code</button>
                </div>
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
          img: "https://picsum.photos/id/1006/500/500",
          more: 'https://drive.google.com/drive/folders/1nF4oy4G7vFhJsOuhYuLx8J7F-98qmicc?usp=sharing',
          git: 'https://github.com/ChangmoKang/PJT'
        },
        {
          id: 2,
          title: 'Sample 2',
          info: 'Then this will state that the font-size of the element should always be 100% of the height of the viewport at all times (50vh would be 50%, 15vh would be 15% and so on).',
          img: "https://picsum.photos/id/101/500/500",
          more: 'https://drive.google.com/drive/folders/1nF4oy4G7vFhJsOuhYuLx8J7F-98qmicc?usp=sharing',
          git: 'https://github.com/ChangmoKang/PJT'
        },
        {
          id: 3,
          title: 'Sample 3',
          info: 'In the demo below try resizing the height of the example to watch the type stretch:',
          img: "https://picsum.photos/id/102/500/500",
          more: 'https://drive.google.com/drive/folders/1nF4oy4G7vFhJsOuhYuLx8J7F-98qmicc?usp=sharing',
          git: 'https://github.com/ChangmoKang/PJT'
        },
        {
          id: 4,
          title: 'Sample 4',
          info: 'In the demo below try resizing the height of the example to watch the type stretch:',
          img: "https://picsum.photos/id/1040/500/500",
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

.projectRow {
  @include maxWidth(960) {
    max-width: 600px;
  }
  @include maxWidth(600) {
    max-width: 300px;
  }
  margin: 0 auto;
}
.projectFlex {
  // border: 1px solid red;
}
.projectBox {
  width: 90%;
  margin: 20px auto;
  height: 170px;
  // border: 1px solid blue;
  border-radius: 5px;
  overflow: hidden;
  position: relative;
  img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: all 0.3s;
  }
  .projectInfo {
    width: 100%; height: 100%;
    position: absolute;
    top: 0; left: 0;
    background: $bgBlack;
    transition: all 0.3s;
    opacity: 0;
    .details {
      height: calc(100% - 50px);
      // border: 1px solid red;
    }
    .btn-box {
      height: 50px;
      display: flex;
      justify-content: space-evenly;
      align-items: baseline;
      padding-top: 7px;
      .btn {
        font-size: 0.8em;
        font-family: $fontContent;
        &:first-child {@include btnSlideRight(white);}
        &:last-child {@include btnSlideLeft(white);}
      }
    }
  }
  &:hover {
    img {transform: scale(1.1);}
    .projectInfo {opacity: 1;}
  }
}

</style>