<template>
  <section class="bookPage">
    <div class="pageContent">
      <p>Skills</p>
    </div>
    <NavArrows :prevLabel="prev.label" :prevName="prev.name" :nextLabel="next" :nextName="next"/>
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

</style>