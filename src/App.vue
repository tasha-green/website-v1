<template>
  <nav>
    <div class="menuBar">
      <div class="logo">
        <p id="firstName">{{ logoFirst }}</p>
        <p id="lastName">{{ logoLast }}</p>
      </div>
      <ul class="navBar">
        <li>
          <div class="dropdown">
            <button class="navItem">{{ workDropdown }}</button>
            <img class="dropdownPic" src="../src/assets/dropdown.png">
            <div class="dropdownContent">
              <a href="components/DesignPage.vue">{{ dropDownOptionDesign }}</a>
              <a href="components/JavascriptPage.vue">{{ dropDownOptionJS }}</a>
              <a href="components/ModellingPage.vue">{{ dropDownOptionModel }}</a>
              <a href="components/UnityPage.vue">{{ dropDownOptionUnity }}</a>
            </div>
          </div>
        </li>
        <li>
          <a class="navItem" href="#" style="padding-top: 6px">{{ contact }}</a>
        </li>
      </ul>
    </div>
  </nav>
  <div class="body">
    <AboutPage/>
    <DesignPage/>
  </div>
</template>

<script>
import AboutPage from './components/AboutPage.vue'
//import JavascriptPage from './components/JavascriptPage.vue'
//import ModellingPage from './components/ModellingPage.vue'
import DesignPage from './components/DesignPage.vue'
//import UnityPage from './components/UnityPage.vue'

export default {
  name: 'App',
  components: {
    AboutPage,
    //JavascriptPage,
    //ModellingPage,
    //UnityPage,
    DesignPage
  },
  data() {
    return {
      logoFirst: "Natasha",
      logoLast: "Green",
      workDropdown: "WORK",
      dropDownOptionDesign: "Design",
      dropDownOptionJS: "Javascript Projects",
      dropDownOptionModel: "Modelling",
      dropDownOptionUnity: "Unity",
      contact: "CONTACT"
    }
  }
}

window.onscroll = function() {
  let nav = document.querySelector("nav");
  if(document.documentElement.scrollTop > 20) {
    nav.classList.add("sticky");
  }
  else {
    nav.classList.remove("sticky");
  }
}

</script>

<style>
* {
  text-decoration: none;
}
.body {
  padding: 78px 0px 0px;
}

.dropdownPic {
  margin-bottom: -6px;
}

.navBar li {
  vertical-align: bottom;
}
body {
  background-color: #F4FCED;
}

nav .menuBar {
  position: fixed;
  top: 0;
  left: 0;
  width: 95%; 
  transition: all 0.4s ease;
}

nav.sticky .menuBar {
  box-shadow: 0 2px 2px rgba(0, 0, 0, 0.075);
}

.menuBar {
  background-color: #FFFFFF;
  padding-left: 30px;
  padding-right: 50px;
  display: flex;
  
}

.navItem {
  background-color: transparent;
  border: transparent;
  color:#000000;
  font-weight: 200;
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 15px;
  padding-left: 10px;
}


.logo {
  display: flex;
  font-size: 25px;
  font-weight: 500;
  font-family: 'Courier New', Courier, monospace;
}

.navBar {
  display: flex;
  align-items: center;
}

ul {
  list-style-type:none;
}


#firstName {
  padding-right: 10px;
}

.dropdown {
  padding-left: 20px;
  display: inline-block;
  position: relative;
}

.dropdownContent {
  display: none;
  background-color: #FFFFFF;
  position: absolute;
  width: 100%;
  overflow: auto;
  box-shadow: 0px 10px 10px 0px rgba(0, 0, 0, 0.1);
}

.dropdown:hover .dropdownContent {
  display:list-item ;
}

.dropdownContent a {
  display: block;
  color: #000000;
  padding: 5px;
  font-weight: 200;
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 15px;
}

.dropdownContent a:hover {
  color: #FFFFFF;
  background-color: #00A4BD;
}

</style>
