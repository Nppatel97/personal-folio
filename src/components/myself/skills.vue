<template>
  <div id="skills">
    <h2>skills</h2>
    <div id="skillSet">
      <div class="skills-container">
        <div class="one" :class="{'animate-skills': scrolled}">
          <img src="../../assets/htmlCssLogo.png" alt>
        </div>
        <div class="two" :class="{'animate-skills': scrolled}">
          <img src="../../assets/jsLogo.png" alt>
        </div>
        <div class="three" :class="{'animate-skills': scrolled}">
          <img src="../../assets/jqLogo.png" alt>
        </div>
        <div class="four" :class="{'animate-skills': scrolled}">
          <img src="../../assets/bootLogo.png" alt>
        </div>
        <div class="five" :class="{'animate-skills': scrolled}">
          <img src="../../assets/vueLogo.png" alt>
        </div>
        <div class="six" :class="{'animate-skills': scrolled}">
          <img src="../../assets/reactLogo.png" alt>
        </div>
        <div class="seven" :class="{'animate-skills': scrolled}">
          <img src="../../assets/javaLogo.png" alt>
        </div>
        <div class="eight" :class="{'animate-skills': scrolled}">
          <img src="../../assets/phpSqlLogo.png" alt>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      scrolled: false
    };
  },
  methods: {
    handleScroll() {
      if (window.scrollY > 250) this.scrolled = true;
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
$burly-dark: rgb(190, 128, 46);

#skills {
  padding: 2rem 1rem;
  text-align: center;
  position: relative;
  width: 100%;
  color: white;
  background: linear-gradient(125deg, burlywood, burlywood, rgb(172, 135, 87));

  h2 {
    text-transform: uppercase;
  }
}

#skillSet {
  overflow: auto;
  margin: 2em auto 1em;
}

.skills-container {
  display: grid;
  grid-gap: 1em;
  padding-left: 2rem;
  grid-template-columns: repeat(auto-fill, 80px);

  img {
    height: 70px;
    width: 70px;
    border-radius: 100px;
    border: 2px solid rgb(190, 128, 46);
    padding: 5px;
  }
}

@keyframes slideIn {
  from {
    transform: translateY(-10px);
    opacity: 0;
  }
  to {
    transform: translateY(0px);
    opacity: 1;
  }
}

.animate-skills {
  animation: slideIn 0.3s ease-in forwards;
}

.one,
.two,
.three,
.four,
.five,
.six,
.seven,
.eight {
  opacity: 0;
  transition: all 0.4s ease;
}

.two {
  animation-delay: 0.1s;
}
.three {
  animation-delay: 0.2s;
}
.four {
  animation-delay: 0.3s;
}
.five {
  animation-delay: 0.4s;
}
.six {
  animation-delay: 0.5s;
}
.seven {
  animation-delay: 0.6s;
}
.eight {
  animation-delay: 0.7s;
}

@media (min-width: 880px) {
  #skills {
    margin-top: 129px;
    padding: 2rem 11rem;

    h2 {
      text-align: left;
    }
  }

  .skills-container {
    padding: 1em 0 2em;
    margin-top: 1em;
    margin-left: 1em;
    display: grid;
    grid-gap: 1em;
    grid-template-columns: repeat(auto-fill, 70px);
  }
}
</style>
