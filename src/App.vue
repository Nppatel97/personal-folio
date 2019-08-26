<template>
  <div id="app">
    <navbar-header></navbar-header>
    <about-me></about-me>
    <my-desc></my-desc>
    <my-skills></my-skills>
    <my-projects></my-projects>
    <my-sideworks></my-sideworks>
    <my-footer></my-footer>
  </div>
</template>

<script>
import navbar from "./components/header/navbar.vue";
import myTag from "./components/myself/headline.vue";
import myself from "./components/myself/myIntro.vue";
import skills from "./components/myself/skills.vue";
import project from "./components/projects/project.vue";
import sideWork from "./components/sideStuff/sideWorks.vue";
import footer from "./components/footer/footer.vue";

export default {
  components: {
    navbarHeader: navbar,
    aboutMe: myTag,
    myDesc: myself,
    mySkills: skills,
    myProjects: project,
    mySideworks: sideWork,
    myFooter: footer
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Kalam|Raleway");

$clr-dark: #272727;
$link-clr: rgb(87, 62, 31);
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: "Raleway", sans-serif;
}

html {
  scroll-behavior: smooth;
  overflow-x: hidden !important;
}

body {
  background-color: whitesmoke;
  overflow-x: hidden !important;
}
</style>
