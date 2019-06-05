<template>
  <div id="header" :style="{backgroundColor: bgColor}">
    <div class="logo">
      <img src="../../assets/npLogo.png" class="img" width="50" height="50">
      <h1>Nisarg Patel</h1>
    </div>

    <input type="checkbox" id="navToggle" class="navi-toggle">
    <nav>
      <ul>
        <li>
          <a href="#about">
            <i class="fas fa-grin-alt icon"></i>About
          </a>
        </li>
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
      bgColor: "transparent",
      clicked: false
    };
  },
  methods: {
    closeNavbar() {},
    handleScroll() {
      this.scrolled = window.scrollY > 10;
      this.scrolled
        ? (this.bgColor = "rgba(39, 39, 39, 0.9)")
        : (this.bgColor = "transparent");
      // console.log(this.scrolled);
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

.transp {
  background: $secondary-bg-clr;
}

.logo {
  position: relative;
  display: inline-flex;
  align-items: center;
  padding: 1em;
}

nav {
  position: absolute;
  text-align: right;
  top: 100%;
  left: 0;
  background: $secondary-bg-clr;
  width: 100%;
  transform: scale(1, 0);
  transform-origin: top;
  transition: transform 400ms ease-in-out;

  ul {
    list-style: none;
  }

  li {
    margin: 1em;
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
    font-size: 1rem;
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
    transform: rotate(360deg);
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

    a {
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
      display: flex;
      margin-bottom: 0;
    }

    li {
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
