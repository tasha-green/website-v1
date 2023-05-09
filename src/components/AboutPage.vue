<template>
    <div class="About">
      <p class="AboutTitle">{{ uxTitle }}</p>
      <p class="AboutTitle">{{ and }}</p>
      <p class="AboutTitle">{{ artTitle }}</p>
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