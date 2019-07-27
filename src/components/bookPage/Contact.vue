<template>
  <section class="bookPage">
    <div class="pageContent">
      <p>Contact</p>
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

</style>
