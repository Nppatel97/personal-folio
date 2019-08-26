<template>
  <div id="about">
    <div class="background">.</div>
    <div class="about-content">
      <div class="img">
        <img src="../../assets/meImg.jpg" alt="My image" height="150" width="150" />
      </div>
      <div class="desc">
        Passionate Web Developer with experience in Web Dev tools like HTML5, CSS/SASS, JavaScript, Vue, React and Java
        <br />
        <br />
        <a href="https://github.com/Nppatel97">
          <i class="fab fa-github"></i>
        </a>
        <a href="https://www.linkedin.com/in/nppatel97/">
          <i class="fab fa-linkedin"></i>
        </a>
        <a
          href="https://github.com/Nppatel97/personal-folio/blob/master/src/assets/Nisarg_Patel_Resume.pdf"
        >
          <i class="fas fa-file-pdf"></i>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Kalam|Raleway");

$clr-dark: #272727;
$link-clr: rgb(87, 62, 31);

.background {
  position: absolute;
  width: 100%;
  height: 75vh;
  background: url("../../assets/bg.png") fixed no-repeat;
  background-size: contain;
  z-index: -100000;
}

.about-content {
  text-align: center;
  align-items: center;
  padding-top: 6rem;
  width: 100%;

  img {
    margin: 1em;
    border-radius: 100%;
    filter: drop-shadow(8px 8px 10px black);
  }
}

.desc {
  font-size: 1.5em;
  padding: 0 5%;
  font-family: "Kalam", cursive;
  background: whitesmoke;
  padding-bottom: 2rem;
  a {
    text-decoration: none !important;
    color: $clr-dark;
    padding: 5px;
    margin: 0 0.5em;

    &:nth-child(4) {
      margin: 0 0.3em;
    }

    svg {
      font-size: 1.7em;
      transition: 0.3s ease;

      &:hover {
        color: $link-clr;
        transform: translateY(-10px);
      }
    }
  }
}

@media (min-width: 880px) {
  // About Me

  .background {
    background-size: cover;
  }

  .about-content {
    display: grid;
    grid-template-columns: 0.25fr auto minmax(600px, 1fr) 1fr;
    color: white;
    text-align: left;
    padding-top: 9rem;
    padding-bottom: 2rem;
  }

  .img {
    grid-column: 2 / span 1;
  }

  .desc {
    grid-column: 3 / span 1;
    color: white;
    z-index: 1;
    background: transparent;
  }

  a {
    text-decoration: none !important;
    color: white;

    svg {
      color: white;
    }
  }
}
</style>
