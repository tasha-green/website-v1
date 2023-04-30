<template>
  <div class="menuBar">
    <div class="logo">
      <p id="firstName">{{ logoFirst }}</p>
      <p id="lastName">{{ logoLast }}</p>
    </div>
    <ul class="navBar">
      <li><a class="navItem" href="#">{{ aboutLink }}</a></li>
      <li><a class="navItem" href="#">{{ workDropdown }}</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
      logoFirst: "Natasha",
      logoLast: "Green",
      aboutLink: "ABOUT",
      workDropdown: "WORK"
    }

  }
}
</script>

<style scoped>
.menuBar {
  background-color: #A9D18E;
  padding-left: 2%;
  padding-right: 2%;
  display: flex;
  justify-content: space-between;
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
  font-size: 15px;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

.navItem {
  padding-left: 10px;
}

ul {
  list-style-type:none;
}


#firstName {
  padding-right: 10px;
}

</style>
