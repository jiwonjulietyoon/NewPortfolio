<template>
  <section class="bookPage">
    <div class="pageContent">
      <p>Project</p>
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
      next: "Contact"
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";

</style>