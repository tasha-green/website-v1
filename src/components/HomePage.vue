<template>
  <div class="hello">
  Hey guys! I have a website!!  
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  text-align: center;
  display: flex;
  justify-content: center;
}
</style>
