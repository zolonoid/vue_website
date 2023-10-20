<template>
  <HeaderComp></HeaderComp>
  <router-view />
  <FooterComp></FooterComp>
</template>

<script>
// @ is an alias to /src
import HeaderComp from '@/components/HeaderComp.vue'
import FooterComp from '@/components/FooterComp.vue'

export default {
  components: {
    HeaderComp,
    FooterComp
  }
}
</script>

<style lang="scss">
// nav {
//   padding: 30px;

//   a {
//     font-weight: bold;
//     color: #2c3e50;

//     &.router-link-exact-active {
//       color: #42b983;
//     }
//   }
// }
</style>
