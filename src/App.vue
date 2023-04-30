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

nav .menuBar {
  position: fixed;
  /*top: 0;
  left: 0;*/
  width: 95%; 
  transition: all 0.4s ease;
}

nav.sticky .menuBar {
  background: #A9D18E;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
}

.menuBar {
  background-color: #FFFFFF;
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
