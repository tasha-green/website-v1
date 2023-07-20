<template>
  <!--<PageLoader/>-->

  <nav class="navbar navbar-expand-lg fixed-top">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">{{ logoFirst }} {{ logoLast }}</a>
      <div class="navbar-contact">
        <span class="material-icons">{{ emailIcon }}</span>
        <div id="liveAlert"></div>
        
        <button class="navbar-contact-email btn btn-link" @click="copy">natasha2green@gmail.com</button>
      </div>
    </div>
  </nav>

  <div class="body py-5">
    <div class="body-progress"></div>
    <div class="body-pages pt-4">
      <AboutPage/>
    </div>
  </div>
</template>

<script>
import AboutPage from './components/AboutPage.vue'
//import PageLoader from './components/PageLoader.vue'

export default {
  name: 'App',
  components: {
    AboutPage,
    //PageLoader
  },
  data() {
    return {
      logoFirst: "Natasha",
      logoLast: "Green",
      emailIcon: "email"
    }
  },
  methods: {
    async copy() {
      let text = "natasha2green@gmail.com";

      try {
        await navigator.clipboard.writeText(text);
        console.log('Content copied to clipboard');

        const alertPlaceholder = document.getElementById('liveAlert');

        const appendAlert = (message) => {
          const wrapper = document.createElement('div')
          wrapper.innerHTML = [
          `<div class="alert alert-dark alert-dismissible fade show">`,
          `   <strong>${message}</strong>`,
          '</div>'
          ].join('');

          alertPlaceholder.append(wrapper);

          setInterval(function () {
            if (!alertPlaceholder.style.opacity) {
                alertPlaceholder.style.opacity = 1;
            }
            if (alertPlaceholder.style.opacity > 0) {
                alertPlaceholder.style.opacity -= 0.05;
            } else {
                clearInterval(alertPlaceholder);
            }
          }, 200);
            
        }

        appendAlert('You\'ve copied the email!')

      } catch(err) {
        console.error('Failed to copy: ', err);
      }
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
  height: 100%;
  z-index: 1;
  --bs-progress-bg: #F4FCED;
}

.body {
  padding: 78px 0px 0px;
  background-color: #F4FCED;
}

.navbar-brand{
  font-family: 'Courier New', Courier, monospace;
}

.navbar-contact {
  display: inline-flex;
}

.navbar-contact-email {
  margin-bottom: 0px;
  padding-right: 20px;
  padding-left: 0%;
  padding-top: 0%;
  padding-bottom: 0%;
  font-family: 'Courier New', Courier, monospace;
  color:black;
}

.material-icons {
  padding-right: 2%;
  vertical-align: middle;
  color:#707070;
}

.navbar {
  z-index: 2;
  background-color: #FFFFFF;
  transition: all 0.4s ease;
}

.alert {
  position: absolute;
  font-size: smaller;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  margin: 0%;
  padding: 15px;
}
</style>
