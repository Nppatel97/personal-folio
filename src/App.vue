<template>
  <div id="app">
    <navbar-header></navbar-header>
    <about-me></about-me>
    <my-desc></my-desc>
    <my-skills></my-skills>
    <my-projects></my-projects>
  </div>
</template>

<script>
import navbar from "./components/header/navbar.vue";
import myTag from "./components/myself/headline.vue";
import myself from "./components/myself/myIntro.vue";
import skills from "./components/myself/skills.vue";
import project from "./components/projects/project.vue";

export default {
  components: {
    navbarHeader: navbar,
    aboutMe: myTag,
    myDesc: myself,
    mySkills: skills,
    myProjects: project
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Kalam|Raleway");

$primary-clr: #b2fdb3;
$primary-bg-clr: rgba(178, 253, 179, 0.9);
$secondary-clr: #22b14c;
$secondary-bg-clr: rgba(34, 177, 77, 0.95);
$clr-dark: #272727;

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
}

body {
  background-color: whitesmoke;
}
</style>
