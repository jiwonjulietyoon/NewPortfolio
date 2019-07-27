<template>
  <section class="bookPage">
    <div class="pageContent">
      <p>About Me</p>
    </div>
    <NavArrows :prevLabel="prev" :prevName="prev" :nextLabel="next" :nextName="next"/>
  </section>
</template>


<script>
import NavArrows from '@/components/NavArrows';

export default {
  name: 'AboutMe',
  components: {
    NavArrows
  },
  data() {
    return {
      prev: "Welcome",
      next: "Skills"
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";

</style>