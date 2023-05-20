<template>
  <nav class="navbar navbar-expand-lg fixed-top">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">{{ logoFirst }} {{ logoLast }}</a>
      <div class="navbar-contact">
        <span class="material-icons">{{ emailIcon }}</span>
        <p class="navbar-contact-email">natasha2green@gmail.com</p>
      </div>
    </div>
  </nav>

  <div class="body">
    <div class="body-progress"></div>
    <div class="body-pages">
      <AboutPage/>
    </div>
  </div>
</template>

<script>
import AboutPage from './components/AboutPage.vue'

export default {
  name: 'App',
  components: {
    AboutPage
  },
  data() {
    return {
      logoFirst: "Natasha",
      logoLast: "Green",
      emailIcon: "email"
    }
  }
}

window.onscroll = function() {

  var winHeight = getWindowHeight();
  var scrollTop = getWindowScroll();
  var docHeight = getDocumentHeight();

  var progress = (scrollTop/ (docHeight - winHeight)) * 100;

  document.querySelector(
          ".body-progress"
        ).style.background = `linear-gradient(to bottom, #6FC18C ${progress}%, #F4FCED ${progress}%)`;
}

function getWindowHeight() {
  return window.innerHeight || document.documentElement.clientHeight || document.body.clientHeight || 0;
}

function getWindowScroll() {
  return window.pageYOffset || document.body.scrollTop || document.documentElement.scrollTop || 0;
}

function getDocumentHeight() {
  return Math.max(document.body.scrollHeight || 0, document.documentElement.scrollHeight || 0, document.body.offsetHeight || 0, document.documentElement.offsetHeight || 0, document.body.clientHeight || 0, document.documentElement.clientHeight || 0);
}


</script>

<style>
* {
  text-decoration: none;
}

.body-progress {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 10px;
  height: 90.5%;
  /*height: 100%;*/
  z-index: 1;
  --bs-progress-bg: #F4FCED;
}

.body {
  padding: 78px 0px 0px;
  background-color: #F4FCED;
}

.navbar-contact {
  display: inline-flex;
}

.navbar-contact-email {
  margin-bottom: 0px;
  padding-bottom: 0px;
}

.material-icons {
  padding-right: 4%;
  vertical-align: middle;
  color:#707070;
}

.navbar {
  z-index: 2;
  background-color: #FFFFFF;
  transition: all 0.4s ease;
}

</style>
