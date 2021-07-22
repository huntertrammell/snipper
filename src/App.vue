<template>
  <header id="fixed-header">
    <app-nav />
  </header>
  <main class="page" id="main">
    <router-view />
  </main>
  <footer>
    <app-footer />
  </footer>
</template>
<script>
import appNav from './components/Nav.vue';
import appFooter from './components/Footer.vue';
export default {
  data(){
    return {
      scrollActive: false
    }
  },
  components: {
    appNav,
    appFooter
  },
  mounted() {
      document.addEventListener('scroll', (e) => {
      let position = document.body.getBoundingClientRect().y;
      let nav = document.getElementById('fixed-header');
      position < -50 ? nav.classList.add('scroll-active') : nav.classList.remove('scroll-active');
      })
  }
}
</script>
<style lang="scss">
//Import google font
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;700;800&display=swap');

//Variables
$font-heading: black;
$font-body: #303030;

//Global Styles
* {
  font-family: 'Poppins', sans-serif;
  font-weight: 400;
  color: $font-body;
}
html, body {
  padding: 0;
  margin: 0;
}
html {
  font-size: 62.5%; /* Now 10px = 1rem! */
}
body {
  font-size: 16px; /* px fallback */
  font-size: 1.8rem; /* default font-size for document */
  line-height: 1.5; /* a nice line-height */
  position: relative;
  @media(max-width: 992px){
    font-size: 1.6
  }
  @media(max-width: 762px){
    font-size: 1.4rem;
  }
}
.container {
  max-width: 1400px;
  margin: 0 auto;
}
header {
  position: fixed;
  width: 100%;
  z-index: 3;
  background-color: rgba($color: #ffffff, $alpha: 0);
  transition: background-color .2s ease;
  &.scroll-active {
        background-color: white;
        box-shadow: 0px 3px 10px -4px rgba(0,0,0,0.4);
  }
  @media (max-width: 1400px) {
    .container {
      padding: 1.5rem 3rem 0 3rem;
    }
  }
}
main {
  @media (max-width: 1400px) {
    .container {
      padding: 0 3rem;
    }
  }
}
footer {
  width: 100%;
  padding: 8rem 0;
  @media (max-width: 1400px) {
    .container {
      padding: 0 3rem 1.5rem 3rem;
    }
  }
  @media(max-width: 762px){
    padding: 4rem 0 2rem;
  }
}
h1 {
  font-weight: 800;
  color: $font-heading;
  font-size: 6rem;
  @media(max-width: 992px){
    font-size: 5rem;
    margin-top: 2rem;
  }
  @media(max-width: 762px){
    font-size: 4rem;
    margin-top: 2rem;
  }
}
h2 {
  font-weight: 700;
  color: $font-heading;
  font-size: 4rem;
  line-height: 1.75;
  margin-bottom: 1.5rem;
  @media(max-width: 762px){
    font-size: 2.5rem;
    line-height: 1.25;
    margin-bottom: 1rem;
  }
}
//Utilities
.text-center {
  text-align: center;
}
</style>
