<template>
  <div id="footer">
    <div id="infoBox">
      <div id="links">
        <h2>Get in Touch</h2>
        <a href="https://codepen.io/Nppatel97">
          <i class="fab fa-codepen"></i>
        </a>
        <a href="https://github.com/Nppatel97">
          <i class="fab fa-github"></i>
        </a>
        <a href="https://www.linkedin.com/in/nppatel97/">
          <i class="fab fa-linkedin-in"></i>
        </a>
        <a href="https://www.facebook.com/profile.php?id=100008371003284">
          <i class="fab fa-facebook-f"></i>
        </a>
      </div>
      <div id="name">By Nisarg Patel</div>
      <div id="btt">
        <a href="#">
          <i class="fas fa-arrow-up"></i>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
$clr-dark: #272727;
$link-clr: rgb(87, 62, 31);

#footer {
  background: $clr-dark;
  padding: 2rem;
  color: white;

  h2 {
    margin-bottom: 1em;
  }
  div {
    padding-left: 1rem;
    text-align: center;
  }

  svg {
    font-size: 1.5em;
    transition: 0.3s ease;

    &:hover {
      transform: translateY(-10px);
    }
  }

  a {
    color: white;
    text-decoration: none;
    padding: 5px;
    margin: 0.5em;

    &:hover {
      color: $link-clr;
    }
  }
}

#name {
  text-align: center !important;
  transform: translateY(20px);
  transition: 0.3s ease;
}

#btt {
  display: none;
}

@media (min-width: 880px) {
  #footer {
    h2 {
      text-align: left;
      margin-bottom: 0.5em;
    }

    div {
      text-align: left;
    }

    a {
      color: white;
      text-decoration: none;
      margin: 0 1em 0 0;
    }
  }

  #links {
    margin-left: 7rem;
  }

  #infoBox {
    display: grid;
    grid-template-columns: 0.5fr 0.5fr 0.5fr;
  }

  #btt {
    display: block;
    padding-right: 5rem;
    transform: translateY(10px);
    transition: 0.3s ease;
    margin-top: 1em;
    text-align: right !important;
  }
}
</style>
