<template>
  <Header />
  <Visual />
  <!-- <Test /> -->
  <Personal />
  <Banner />
  <Footer />
</template>

<script>
import Header from './components/Header.vue';
import Visual from './components/Visual.vue';
import Personal from './components/Personal.vue';
import Banner from './components/Banner.vue';
import Footer from './components/Footer.vue';
// import Test from './components/Test.vue';

export default {
  name: 'App',
  components: {
    Header,
    Visual,
    Personal,
    Banner,
    Footer,
    // Test
  },
  data() {
    return {
    }
  },
}
</script>

<style lang="scss">
@charset "uft-8";

* {
  margin: 0;
  padding: 0;
  font-family: 'Noto Sans KR';
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
  color: #000;
}

img {
  vertical-align: middle;
}</style>
