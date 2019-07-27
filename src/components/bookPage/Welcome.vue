<template>
  <section class="bookPage">
    <div class="pageContent">
      <p>Welcome</p>
    </div>
    <NavArrows :prevActive="false" :nextLabel="next.label" :nextName="next.name"/>
  </section>
</template>


<script>
import NavArrows from '@/components/NavArrows';

export default {
  name: 'Welcome',
  components: {
    NavArrows
  },
  data() {
    return {
      next: {
        label: "About Me",
        name: "AboutMe"
      }
    }
  }
}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";

</style>
