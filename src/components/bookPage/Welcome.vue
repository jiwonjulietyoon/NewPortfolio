<template>
  <section class="bookPage">
    <div class="pageContent">
      <p>Welcome</p>
      <router-link to="/aboutme">About Me</router-link>
    </div>
    <NavArrows />
  </section>
</template>


<script>
import NavArrows from '@/components/NavArrows';

export default {
  name: 'Welcome',
  components: {
    NavArrows
  }
}
</script>

<style lang="scss" scoped>
@import "@/css/style.scss";

</style>
