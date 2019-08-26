<template>
  <div id="sideWork">
    <h2>Side Works</h2>
    <div class="sw-box">
      <div id="swOne">
        <img src="../../assets/ssGif.gif" alt />
        <div class="gif-overlay">
          <div>
            <h3>Slide Show</h3>
            <br />
            <br />
            <br />
            <a href="https://codepen.io/Nppatel97/pen/KLOgvg">
              <i class="fab fa-codepen"></i>
              <br />
              <small>View in Codepen</small>
            </a>
          </div>
        </div>
      </div>
      <div id="swTwo">
        <img src="../../assets/tttGif.gif" alt />
        <div class="gif-overlay">
          <div>
            <h3>Tic Tac Toe</h3>
            <br />
            <br />
            <br />
            <a href="https://codepen.io/Nppatel97/pen/rEPbzj">
              <i class="fab fa-codepen"></i>
              <br />
              <small>View in Codepen</small>
            </a>
          </div>
        </div>
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
#sideWork {
  margin-bottom: 1.5rem;
  h2 {
    padding: 0.5rem;
  }
}

.side-card-parent {
  display: block;
}

.side-card-container {
  padding-top: 1rem;
  display: grid;
  grid-column: 2 / 3;
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

.sw-box {
  width: 100vw;
  margin-top: 1em;
  justify-content: center;

  img {
    height: 100%;
  }
}

#swOne,
#swTwo {
  position: relative;
}

.gif-overlay {
  position: absolute;
  background: linear-gradient(
    to top,
    black,
    rgba(0, 0, 0, 0.8),
    rgba(0, 0, 0, 0.5)
  );
  top: 0;
  left: 0;
  height: 100%;
  width: 101%;
  transform: scale(1, 0);
  transition: 0.3s ease;
  text-align: center;
  transform-origin: bottom;

  div {
    position: absolute;
    color: white;
    padding: 50px;
    width: 300px;
    height: 50px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -5%);
  }

  svg {
    font-size: 2em;
    transition: 0.3s ease;
  }

  a {
    color: white;
    text-decoration: none;
  }

  a:hover svg {
    transform: translateY(-10px);
  }
}

#swOne:hover .gif-overlay,
#swTwo:hover .gif-overlay {
  transform: scale(1, 1);
}

@media (min-width: 880px) {
  .side-card-container {
    grid-template-columns: repeat(auto-fit, 355px);
  }

  .side-card-parent {
    display: grid;
    grid-template-columns: 0.5fr minmax(500px, 3fr) 0.5fr;
  }

  #sideWork h2 {
    text-align: left;
    padding-left: 11rem;
  }

  .sw-box {
    display: inline-flex;
    justify-content: center;
  }
}
</style>
