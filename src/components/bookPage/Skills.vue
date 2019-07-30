<template>
  <section class="bookPage">
    <div class="pageContainer">
      <h2 class="pageHeader">Skills</h2>
      <div class="content">
        <div class="ranked">
          <div class="left">
            <div class="sideMain">
              <div class="rod"></div>
              <div class="top">
                <div></div>
                <div></div>
                <div></div>
                <div></div>
              </div>
              <div class="hornLeft"></div>
              <div class="text">HTML</div>
            </div>
          </div>
          <div class="right">
            <div class="sideMain">
              <div class="rod"></div>
              <div class="top">
                <div></div>
                <div></div>
                <div></div>
                <div></div>
              </div>
              <div class="hornRight"></div>
              <div class="text">JavaScript</div>
            </div>
          </div>
          <div class="center">
            <div class="main">
              <div class="rod">
                <div class="deco"></div>
                <div class="deco"></div>
              </div>
              <div class="top"></div>
              <div class="top"></div>
              <div class="top"></div>
              <div class="top"></div>
              <div class="text">CSS</div>
            </div>
          </div>
        </div>
        <div class="others">
          <div class="roll">
            <div class="top"></div>
            <div class="bot"></div>
          </div>
          <div class="main">
            Python, Django, Vue.js, Bootstrap, JQuery, SQLite, Linux
          </div>
          <div class="roll">
            <div class="top"></div>
            <div class="bot"></div>
          </div>
        </div>
      </div>
    </div>
    <NavArrows :prevLabel="prev.label" :prevName="prev.name" :nextLabel="next" :nextName="next" />
  </section>
</template>


<script>
import NavArrows from '@/components/NavArrows';

export default {
  name: 'Skills',
  components: {
    NavArrows
  },
  data() {
    return {
      prev: {
        label: "About Me",
        name: "AboutMe"
      },
      next: "Projects"
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";

.content {
  width: 100%;
  overflow-y: auto;
}
.ranked {
  width: 90%;
  height: 250px;
  margin: 0 auto 30px;
  position: relative;
}
.center {
  position: absolute;
  left: 50%;
  top: 40px;
  transform: translate(-50%);
  width: 150px;
  height: 150px;
  & > .main {
    position: absolute;
    width: 100%;
    height: 100%;
    background: #DCDCC6;
    &::before, &::after {
      position: absolute;
      width: 0;
      height: 0;
      top: 100%;
      border-top: 50px solid #DCDCC6;
    }
    &::before {
      border-right: 75px solid transparent;
    }
    &::after {
      border-left: 75px solid transparent;
      right: 0;
    }
    & > .rod {
      width: 230px;
      height: 10px;
      background-color: #003694;
      position: absolute;
      top: -25px;
      left: -40px;
      &::before, &::after {
        position: absolute;
        width: 10px;
        height: 18px;
        background: #003694;
        top: -4px;
        border-radius: 2px;
      }
      &::before {left: -10px;}
      &::after {right: -10px;}
      & > .deco {
        width: 20px; height: 20px;
        border-radius: 50%;
        background: #003694;
        position: absolute;
        top: -5px;
        &:first-child {left: -27px;}
        &:last-child {right: -27px;}
      }
    }
    & > .top {
      position: absolute;
      width: 30px;
      height: 30px;
      background-color: #DCDCC6;
      bottom: 100%;
      &:nth-of-type(2) {left: 40px;}
      &:nth-of-type(3) {right: 40px;}
      &:nth-of-type(4) {right: 0;}
    }
    & > .text {
      position: absolute;
      width: 100%; height: 100%;
      line-height: 150px;
      text-align: center;
      font-family: $fontFancy;
      font-size: 1.5em;
    }
  }
}




.left {
  width: 120px;
  height: 120px;
  position: absolute;
  top: 100px;
  left: 10%;
}
.sideMain {
  position: absolute;
  width: 100%;
  height: 100%;
  background: beige;
  &::after {
    position: absolute;
    top: 100%;
    width: 0;
    height: 0;
    border-left: 60px solid transparent;
    border-right: 60px solid transparent;
    border-top: 20px solid beige;
  }
  & > .rod {
    width: 160px;
    height: 10px;
    background: gold;
    position: absolute;
    top: 5px;
    left: -20px;
    &::before, &::after {
      position: absolute;
      width: 10px;
      height: 16px;
      background: gold;
      border-radius: 5px;
      top: -3px;
    }
    &::before {left: -5px;}
    &::after {right: -5px;}
  }
  & > .top {
    width: 100%;
    height: 20px;
    background: #004ac9;
    position: absolute;
    & > div {
      width: 26px;
      height: 10px;
      background: #004ac9;
      position: absolute;
      top: 100%;
      border-radius: 0 0 3px 3px;
      &:nth-of-type(2) {left: 31px;}
      &:nth-of-type(3) {right: 31px;}
      &:nth-of-type(4) {right: 0px;}
    }
  }
  & > .text {
    position: absolute;
    width: 100%;
    height: 90px;
    line-height: 90px;
    text-align: center;
    top: 30px; left: 0;
    font-family: $fontFancy;
    font-size: 1.5em;
  }
}
.hornLeft {
  width: 0;
  height: 0;
  border-top: 25px solid transparent;
  border-left: 40px solid gold;
  border-bottom: 25px solid transparent;
  position: absolute;
  top: -15px;
  left: -50px;
  &::after {
    position: absolute;
    width: 7px;
    height: 56px;
    background: rgb(221, 188, 0);
    border-radius: 3px;
    left: -47px;
    top: -27px;
  }
}

.right {
  width: 120px;
  height: 120px;
  position: absolute;
  top: 100px;
  right: 10%;
}
.hornRight {
  width: 0;
  height: 0;
  border-top: 25px solid transparent;
  border-right: 40px solid gold;
  border-bottom: 25px solid transparent;
  position: absolute;
  top: -15px;
  right: -50px;
  &::after {
    position: absolute;
    width: 7px;
    height: 56px;
    background: rgb(221, 188, 0);
    border-radius: 3px;
    right: -47px;
    top: -27px;
  }
}






@media screen and (max-width: 575px) {
    .skillsRanked {
        height: 600px;
    }
    .skillCenterOuter {
        top: 40px;
    }
    .skillLeftOuter {
        left: 50%;
        top: 280px;
        transform: translate(-50%);
    }
    
    .skillRightOuter {
        right: initial;
        left: 50%;
        top: 460px;
        transform: translate(-50%);
    }
}




/* * * * * * * * * * * * * * * * * * * * * * * * * */

.skillsOthers {
    width: 80%;
    height: 140px;
    margin: 20px auto;
}
@media screen and (max-width: 575px) {
    .skillsOthers {
        width: 90%;
    }
}
.skillsOthers > div {
    float: left;
}

.skillScrollMain {
    width: calc(100% - 60px);
    height: 100px;
    background-color: beige;
    padding: 10px 20px;
    position: relative;
    top: 10px;
    font-family: 'Berkshire Swash', cursive;
    font-size: 1.3em;
    letter-spacing: 1px;
    font-style: italic;
}

.skillScrollRoll {
    width: 30px;
    height: 120px;
    background-color: #DCDCC6;
    position: relative;
    border-radius: 2px;
}
.skillScrollRoll > .rollTop, .skillScrollRoll > .rollBot {
    position: absolute;
    width: 20px;
    height: 7px;
    background-color: #C4C4B0;
    left: 5px;
}
.skillScrollRoll > .rollTop, .skillScrollRoll > .rollTop:after {
    bottom: 100%;
    border-radius: 2px 2px 0 0;
}
.skillScrollRoll > .rollBot, .skillScrollRoll > .rollBot:after{
    top: 100%;
    border-radius: 0 0 2px 2px;
}
.skillScrollRoll > .rollTop:after, .skillScrollRoll > .rollBot:after {
    content: "";
    position: absolute;
    width: 30%;
    height: 100%;
    background-color: #ABAB9A;
    left: 50%;
    transform: translate(-50%);
}

</style>