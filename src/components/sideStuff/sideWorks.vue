<template>
  <div id="sideWork">
    <h2>Side Works</h2>
    <div class="side-card-parent">
      <div class="side-card-container">
        <pro-card
          :class="{'animate-pro-cards': scrolled}"
          vId="1"
          name="Personal Folio"
          :img="personal"
          link="https://github.com/Nppatel97/personal-folio"
        ></pro-card>
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
  padding: 2rem 0.5rem;
}

.side-card-parent {
  display: block;
  // grid-template-columns: 0.5fr minmax(500px, 3fr) 0.5fr;
}

.side-card-container {
  padding-top: 1rem;
  display: grid;
  grid-column: 2 / 3;
  // grid-gap: 30px;
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
}
</style>
