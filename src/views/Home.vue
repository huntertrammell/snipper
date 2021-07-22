<template>
  <section role="contentinfo" aria-label="Introduction to Company" class="page_hero">
    <div class="page_hero-bkg">
      <div class="container text-center">
        <div class="page_hero-copy">
          <h1>Gorgeous Code Snippets</h1>
          <p>With Snipper, create fully custommizable code snippets in a matter of seconds right from your&nbsp;browser.</p>
          <app-btn url="#" text="Get started" caption="&mdash; it's free" />
          <p>No credit card required.</p>
        </div>
        <div class="page_hero-img">
          <img src="../assets/Snippet_Image.png" alt="Example code snippet" width="1400" height="488">
        </div>
      </div>
    </div>
  </section>
  <section role="contentinfo" aria-label="Product Features" class="page_about">
    <div class="container">
      <div class="page_about-copy">
        <h2>A fully customizable code snippet editor</h2>
        <p>Fully customize the olor schele of your code snippet or use out own premade color schemes. Export your code snippets in JPG, PDF, or any of the other 10+ common extensions.</p>
        <app-btn url="#" text="Get started" caption="&mdash; it's free" />
      </div>
      <div class="page_about-img">
        <img src="../assets/Customizable_Image.png" alt="Color scheme example" width="422" height="376">
      </div>
    </div>
  </section>
</template>
<style lang="scss">
.page {
  position: relative;
  width: 100%;
  top: 0;
  z-index: 1;
  &_hero {
    &-bkg {
      background-image: url('../assets/Background.png');
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;
    }
    .container {
      padding-top: 14rem;
      @media(max-width: 762px) {
          padding-top: 10rem;
      }
    }
    &-copy {
      h1 {
        margin-bottom: 0;
      }
      p {
        width: 50%;
        margin: 0 auto;
        padding: 3rem 1rem;
        @media(max-width: 992px){
          padding: 3rem 1rem;
          width: 75%;
        }
      }
    }
    &-img {
      padding-top: 4rem;
      img {
        width: 100%;
        height: 100%;
        display: block;
      }
    }
  }
  &_about {
    padding-top: 10rem;
    .container {
      display: flex;
      align-items: center;
      @media(max-width: 992px){
        flex-direction: column-reverse;
      }
    }
    &-copy, &-img {
      position: relative;
    }
    &-copy {
      flex: 0 1 60%;
      min-width: 0;
      max-width: 60%;
      margin-right: 4rem;
      @media(max-width: 992px){
        flex: 0 1 100%;
        max-width: 100%;
        margin-right: 0;
      }
    }
    &-img {
      flex: 0 1 40%;
      min-width: 0;
      max-width: 40%;
      @media(max-width: 992px){
        padding-bottom: 3rem;
      }
      img {
        display: block;
        min-height: 0;
        width: 100%;
        height: 100%;
        @media(max-width: 992px){
          width: 50%;
          margin: 0 auto;
        }
        @media(max-width: 762px){
          width: 100%;
        }
      }
      @media(max-width: 992px){
        flex: 0 1 100%;
        max-width: 100%;
      }
    }
  }
} 
</style>
<script>
import appBtn from '../components/Btn.vue'
export default {
  name: "Home",
  components: {
    appBtn
  }
};
</script>
