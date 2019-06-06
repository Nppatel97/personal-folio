<template>
  <div id="proCards">
    <div class="card-body">
      <img :src="`${this.img}`" alt="Project Image">
      <div class="num-img">
        <div class="number">
          <div class="num-txt">{{vId}}</div>
        </div>
        <div class="project-name">{{name}}</div>
      </div>
      <p>
        <slot></slot>
      </p>
      <a :href="`${this.link}`" target="_blank">
        <button class="btn">
          <div>
            <i class="fas fa-arrow-right"></i>
          </div>
        </button>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: ["vId", "name", "img", "link"],
  data() {
    return {
      bgImg: `url(${this.img}) no-repeat`
    };
  }
};
</script>

<style lang="scss">
.card-body {
  width: inherit;
  height: 324px;
  background: linear-gradient(
      170deg,
      rgb(87, 62, 31),
      burlywood,
      rgb(133, 97, 51)
    )
    fixed;
  background-size: cover;

  img {
    width: 100%;
    transition: 0.3s ease;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
  }

  p {
    padding: 1em;
    padding-bottom: 2em;
    background: white;
    transform: translateY(50px);
    opacity: 0;
    transform-origin: top;
    transition: 0.3s ease-in-out;
  }

  button {
    position: relative;
    text-transform: uppercase;
    background: white;
    color: burlywood;
    border: 1px solid burlywood;
    padding: 1em 2em;
    transition: 0.2s ease-in-out;
    cursor: pointer;
    float: right;
    margin-right: 20px;
    margin-top: -25px;
    transform: translateY(-30px);
    z-index: 1;
    transition: 0.3s ease-in-out 0.2s;
    opacity: 0;

    &:hover {
      background: rgb(224, 224, 224);
    }
  }
}

.project-name {
  position: absolute;
  text-transform: uppercase;
  color: white;
  font-weight: bolder;
  font-size: 23px;
  width: 100%;
  z-index: 3;
  transform: scale(0, 1);
  transition: 0.3s ease;
  transform-origin: right;
  background: url("../../assets/burly.jpg") no-repeat;
  background-size: cover;
  padding: 1.8em 0;
  padding-left: 5.5em;
}

.card-body:hover .project-name {
  transform: scale(1, 1);
}

.num-img {
  display: inline-flex;
  overflow: hidden;
}

.number {
  background: transparent;
  padding: 0.5em 1em;
  width: 100%;
  z-index: 5;
  color: white;
  font-size: 50px;
  font-weight: 1000;
  transition: 0s ease-in;
}

.card-body:hover .number {
  background: linear-gradient(
    to right,
    burlywood,
    burlywood,
    burlywood,
    transparent
  );
  transition: 0.3s ease-in;
}

.num-txt {
  opacity: 0;
  transform: translate(-25px, 25px);
}

.card-body:hover .num-txt {
  transform: translate(-25px, 0);
  transition: 0.3s ease;
  opacity: 1;
}

.card-body:hover p {
  transform: translateY(0);
  opacity: 1;
}

.card-body:hover button {
  transform: translateY(0);
  opacity: 1;
}
</style>
