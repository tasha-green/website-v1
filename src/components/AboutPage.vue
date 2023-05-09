<template>
  <div class="myBody">
    <div class="About">
      <!--<p class="AboutTitle">{{ uxTitle }}</p>
      <p class="AboutTitle">{{ and }}</p>
      <p class="AboutTitle">{{ artTitle }}</p>-->
    </div>
    <p class="NotReady">
        My portfolio isn't ready yet! Please come back later.
    </p>
  </div>
  </template>
  
<script>
export default {
  name: 'AboutPage',
  data() {
    return {
      uxTitle: "UX Developer",
      and: "&",
      artTitle: "Artist"
    }
  }
}
</script>

<style scoped>

.myBody {
  display: flex;
}
.NotReady {
  padding-top: 40px;
  padding-left: 20px;
  color:#000000;
  font-weight: 200;
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 60px;

}
.about {
  padding-top: 78;
}
.AboutTitle {
  color:#000000;
  font-weight: 200;
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 60px;
  margin-left: 40px;
}
</style>