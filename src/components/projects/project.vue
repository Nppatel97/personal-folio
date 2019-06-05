<template>
  <div id="project">
    <h2>My Works</h2>
    <div class="card-container">
      <pro-card
        class="p-one"
        :class="{'animate-pro-cards': scrolled}"
        vId="1"
        name="murrayville"
        :img="murrayImg"
      >Wellll helllloooo</pro-card>
      <pro-card
        class="p-two"
        :class="{'animate-pro-cards': scrolled}"
        vId="2"
        name="schedulearn"
        :img="schedImg"
      >me tow helllloooooo</pro-card>
      <pro-card
        class="p-three"
        :class="{'animate-pro-cards': scrolled}"
        vId="3"
        name="symphonia"
        :img="sympImg"
      >i am threee</pro-card>
    </div>
  </div>
</template>

<script>
import card from "./projectCard.vue";
import img1 from "../../assets/murrayville.png";
import img2 from "../../assets/schedulearn.png";
import img3 from "../../assets/symphonia.png";
export default {
  data() {
    return {
      murrayImg: img1,
      schedImg: img2,
      sympImg: img3,
      scrolled: false
    };
  },
  components: {
    proCard: card
  },
  methods: {
    handleScroll() {
      if (window.scrollY > 500) this.scrolled = true;
      // console.log(this.scrolled + window.scrollY);
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
#project {
  padding: 2rem 0.5rem;
}

h2 {
  text-transform: uppercase;
  text-align: center;
}

.card-container {
  padding-top: 1rem;
  display: grid;
  grid-template-columns: repeat(auto-fit, 100%);
}

@keyframes slideSide {
  from {
    transform: translateX(-20px);
    opacity: 0;
  }
  to {
    transform: translateY(0px);
    opacity: 1;
  }
}

.animate-pro-cards {
  animation: slideSide 0.3s ease-in forwards;
}

.p-one,
.p-two,
.p-three {
  opacity: 0;
}

.p-two {
  animation-delay: 0.3s;
}

.p-three {
  animation-delay: 0.6s;
}

@media (min-width: 880px) {
  .card-container {
    padding: 1rem 11rem;
    grid-template-columns: repeat(auto-fit, 24.9vw);
  }

  #project h2 {
    text-align: left;
    padding-left: 11rem;
  }
}
</style>
