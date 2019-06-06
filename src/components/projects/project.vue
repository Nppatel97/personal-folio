<template>
  <div id="project">
    <h2>My Works</h2>
    <div class="card-parent">
      <div class="card-container">
        <pro-card
          class="p-one"
          :class="{'animate-pro-cards': scrolled}"
          vId="1"
          name="Personal Folio"
          :img="personal"
          link="https://github.com/Nppatel97/personal-folio"
        >
          <div class="toolsAndLink">
            <p>
              <strong>Tools used</strong>
              <br>Vue.js v3, Webpack, Hosted on GitHub
            </p>
            <p>
              The website that you are currently browsing is made using Vue.js on Webpack template. It gave me a lot of
              experience on how Vue.js works and its powerful features!
            </p>
          </div>
        </pro-card>
        <pro-card
          class="p-two"
          :class="{'animate-pro-cards': scrolled}"
          vId="2"
          name="murrayville"
          :img="murrayImg"
          link="https://www.murrayvillephysio.ca/"
        >
          <div class="toolsAndLink">
            <p>
              <strong>Tools used</strong>
              <br>HTML, CSS, jQuery, Bootstrap v4
            </p>
            <p>
              This is my first client website made for a clinic in Langley. I have used a lot of Bootstrap items and functionalities
              like margins, paddings, containers, accordian, navbar etc.
            </p>
          </div>
        </pro-card>
        <pro-card
          class="p-three"
          :class="{'animate-pro-cards': scrolled}"
          vId="3"
          name="schedulearn"
          :img="schedImg"
          link="https://schedulearn.com/"
        >
          <div class="toolsAndLink">
            <p>
              <strong>Tools used</strong>
              <br>HTML, CSS, jQuery, Bootstrap, Python, Django
            </p>
            <p>
              A group project built by my friends outside school. My task was to build mobile friendly
              interfaces and webpages for the website.
            </p>
          </div>
        </pro-card>
        <pro-card
          class="p-four"
          :class="{'animate-pro-cards': scrolled}"
          vId="4"
          name="symphonia"
          :img="sympImg"
          link="https://nppatel97.github.io/InfoVizProject/"
        >
          <div class="toolsAndLink">
            <p>
              <strong>Tools used</strong>
              <br>HTML, CSS, jQuery, Bootstrap, Python, Zingchart
            </p>
            <p>
              A school time group project built by me and my group mates. It analyzes different songs from a spotify playlist, displays
              and compares them in visual charts
            </p>
          </div>
        </pro-card>
      </div>
    </div>
  </div>
</template>

<script>
import card from "./projectCard.vue";
import img1 from "../../assets/personalSite.png";
import img2 from "../../assets/murrayville.png";
import img3 from "../../assets/schedulearn.png";
import img4 from "../../assets/symphonia.png";
export default {
  data() {
    return {
      personal: img1,
      murrayImg: img2,
      schedImg: img3,
      sympImg: img4,
      scrolled: false
    };
  },
  components: {
    proCard: card
  },
  methods: {
    handleScroll() {
      if (window.scrollY > 420) this.scrolled = true;
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

.card-parent {
  display: block;
  // grid-template-columns: 0.5fr minmax(500px, 3fr) 0.5fr;
}

.card-container {
  padding-top: 1rem;
  display: grid;
  grid-column: 2 / 3;
  grid-gap: 30px;
  grid-template-columns: repeat(auto-fit, 100%);
}

.toolsAndLink {
  text-align: center;
  p {
    padding: 0.5em;
  }
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
.p-three,
.p-four {
  opacity: 0;
}

.p-two {
  animation-delay: 0.3s;
}

.p-three {
  animation-delay: 0.6s;
}

.p-four {
  animation-delay: 0.9s;
}

@media (min-width: 880px) {
  .card-container {
    grid-template-columns: repeat(auto-fit, 355px);
  }

  .card-parent {
    display: grid;
    grid-template-columns: 0.5fr minmax(500px, 3fr) 0.5fr;
  }

  #project h2 {
    text-align: left;
    padding-left: 11rem;
  }
}
</style>
