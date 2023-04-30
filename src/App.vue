<template>
  <nav>
    <div class="menuBar">
      <div class="logo">
        <p id="firstName">{{ logoFirst }}</p>
        <p id="lastName">{{ logoLast }}</p>
      </div>
      <ul class="navBar">
        <li><a class="navItem" href="#">{{ aboutLink }}</a></li>
        <li>
          <div class="dropdown">
            <button class="navItem">{{ workDropdown }}</button>
            <div class="dropdownContent">
              <a href="#">{{ dropDownOptionDesign }}</a>
              <a href="#">{{ dropDownOptionJS }}</a>
              <a href="#">{{ dropDownOptionModel }}</a>
              <a href="#">{{ dropDownOptionUnity }}</a>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </nav>

  <HomePage/>
</template>

<script>
import HomePage from './components/HomePage.vue'

let nav = document.querySelector("nav");
window.onscroll = function() {
  if(document.documentElement.scrollTop > 30) {
    nav.classList.add("sticky");
  }
  else {
    nav.classList.remove("sticky");
  }
}

export default {
  name: 'App',
  components: {
    HomePage
  },
  data() {
    return {
      logoFirst: "Natasha",
      logoLast: "Green",
      aboutLink: "ABOUT",
      workDropdown: "WORK",
      dropDownOptionDesign: "Design",
      dropDownOptionJS: "Javascript Projects",
      dropDownOptionModel: "Modelling",
      dropDownOptionUnity: "Unity"

    }
  }
}
</script>

<style>
* {
  text-decoration: none;
}

nav.sticky {
  background: #00A4BD;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.4);
}
.menuBar {
  background-color: #A9D18E;
  padding-left: 30px;
  padding-right: 50px;
  display: flex;
  justify-content: space-between;
}

.navItem {
  background-color: transparent;
  border: transparent;
  color:#000000;
  font-weight: 200;
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 15px;
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
