<template>
  <div id="header" :style="{backgroundColor: bgColor}">
    <input type="checkbox" id="navToggle" class="navi-toggle" />
    <div class="logo">
      <a href="#">
        <img src="../../assets/npLogo.png" width="50" height="50" />
        <h1>Nisarg Patel</h1>
      </a>
    </div>

    <nav>
      <ul>
        <li>
          <a href="#skills">
            <i class="fas fa-code icon"></i>
            Skills
          </a>
        </li>
        <li>
          <a href="#project">
            <i class="fas fa-tasks icon"></i>
            Projects
          </a>
        </li>
        <li>
          <a href="#sideWork">
            <i class="fas fa-grin-alt icon"></i>Side Works
          </a>
        </li>
        <li>
          <a href="#contact">
            <i class="fas fa-paper-plane icon"></i>
            Contact
          </a>
        </li>
      </ul>
    </nav>
    <label for="navToggle" class="navi-toggle-label">
      <span></span>
    </label>
  </div>
</template>

<script>
export default {
  data() {
    return {
      scrolled: false,
      bgColor: "transparent"
    };
  },
  methods: {
    handleScroll() {
      this.scrolled = window.scrollY > 10;
      this.scrolled
        ? (this.bgColor = "rgba(39, 39, 39, 1)")
        : (this.bgColor = "transparent");
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
@import url("https://fonts.googleapis.com/css?family=Kalam|Raleway");

$primary-clr: #b2fdb3;
$primary-bg-clr: rgba(178, 253, 179, 0.9);
$secondary-clr: #22b14c;
$secondary-bg-clr: rgba(39, 39, 39, 0.9);
$clr-dark: #272727;

#header {
  color: whitesmoke;
  top: 0;
  z-index: 1000;
  background: transparent;
  position: fixed;
  width: 100%;
  transition: all 400ms ease;

  h1 {
    margin-left: 0.25em;
    font-family: "Kalam", cursive;
    font-weight: 100;
  }
}

.logo {
  position: relative;
  align-items: center;
  padding: 1em;
  cursor: pointer;

  a {
    text-decoration: none;
    all: unset;
    display: inline-flex;
    &:hover {
      color: whitesmoke;
    }
  }
}

nav {
  position: absolute;
  text-align: center;
  top: 0%;
  left: 0;
  background: linear-gradient(to bottom, $clr-dark, $secondary-bg-clr);
  width: 100%;
  transform: scale(1, 0);
  transform-origin: top;
  transition: transform 400ms ease-in-out;
  height: 100vh;

  ul {
    list-style: none;
    margin: 5rem 1rem 0 0;
  }

  li {
    margin: 5rem 2rem 0 0;
  }

  .icon {
    margin-right: 0.3em;
    transform: scale(0, 1);
    transform-origin: center;
    transition: all 150ms ease-in-out;
  }

  a {
    color: whitesmoke;
    text-decoration: none;
    font-size: 2rem;
    text-transform: uppercase;
    opacity: 0;
    transition: opacity 150ms ease-in-out;

    &:hover {
      text-decoration: none;

      .icon {
        transform: scale(1, 1);
      }
    }
  }
}

.navi-toggle {
  display: none;
}

.navi-toggle:checked ~ nav {
  transform: scale(1, 1);

  a {
    opacity: 1;
    transition: opacity 250ms ease-in-out 250ms;
  }
}

.navi-toggle:checked ~ .navi-toggle-label {
  span::before,
  span::after {
    transform: scale(0.3, 1);
  }

  span {
    transform: rotate(180deg);
  }
}

.navi-toggle-label {
  position: absolute;
  top: 0;
  right: 0;
  margin-right: 1em;
  height: 100%;
  display: flex;
  align-items: center;
  cursor: pointer;

  span,
  span::before,
  span::after {
    content: "";
    display: block;
    background: white;
    height: 1.6px;
    width: 2em;
    border-radius: 5px;
    position: relative;
    transition: all 400ms ease-in-out;
  }

  span {
    &::before,
    &::after {
      content: "";
      position: absolute;
    }

    &::before {
      bottom: 8px;
    }

    &::after {
      top: 8px;
    }
  }
}

@media (min-width: 880px) {
  // Navbar

  .navi-toggle-label {
    display: none;
  }

  #header {
    display: grid;
    grid-template-columns: 0.5fr auto minmax(600px, 3fr) 0.5fr;
    background: rgba(39, 39, 39, 0.9);
  }

  .logo {
    grid-column: 2 / span 1;
  }

  nav {
    all: unset;
    grid-column: 3 / span 1;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    height: auto;

    a {
      font-size: 1em;
      opacity: 1;
      position: relative;

      &::after {
        content: "";
        display: block;
        height: 3px;
        background: white;
        position: absolute;
        border-radius: 100px;
        top: 1.5em;
        left: 0;
        right: 0;
        transform: scale(0, 1);
        transition: transform ease-in-out 250ms;
      }

      &:hover::after {
        transform: scale(1, 1);
      }
    }

    ul {
      all: unset;
      display: flex;
      margin-bottom: 0;
    }

    li {
      all: unset;
      margin-left: 2.3em;
      margin-bottom: 0;
      margin-top: 0;
    }
  }

  .icon {
    display: none;
  }
}
</style>
