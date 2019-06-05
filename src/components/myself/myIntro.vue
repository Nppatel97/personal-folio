<template>
  <div id="myself">
    <div class="myself-bg"></div>
    <div class="container" :style="{top: `${topy}px`}">
      <h2>Who I am</h2>
      <p>
        My name is Nisarg Patel and I am a recent graduate from the University of Victoria in Canada.
        I am an aspiring Front-End Developer who loves creating stunning and beautiful user interfaces that deliver the best user experience!
        <br>
        <br>I love keeping myself up-to-date with the latest tech in the industry so I constantly keep learning new things!
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      scrolled: false,
      topy: 0
    };
  },
  methods: {
    handleScroll() {
      // this.scrolled = window.scrollY > 10;
      const scrolly = Math.floor(window.scrollY / -2);
      this.topy = scrolly;
      // console.log(this.topy);
    }
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  }
};
</script>

<style lang="scss">
#myself {
  position: relative;
}
.container {
  position: absolute;
  // top: 10vh;
  right: 10vw;
  min-width: 27vw;
  width: 27vw;
  background: #272727;
  outline: 2px solid burlywood;
  outline-offset: -2em;
  color: white;
  padding: 3.5em;
  text-align: center;
  z-index: 2;
  box-shadow: 0px 0px 10px 3px black;

  h2 {
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    background: #272727;
    padding: 0.6em 0.3em;
  }
}

@media (max-width: 880px) {
  .container {
    right: 0;
    width: 100vw;
    position: relative;
    top: 0 !important;
    box-shadow: none;
  }
}
</style>
