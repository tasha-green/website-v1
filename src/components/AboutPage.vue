<template>
  <div class="container">
    <div class="overlay">
        <p class="aboutTitle">{{ uxTitle }}</p>
        <p class="aboutTitle">{{ and }}</p>
        <p class="aboutTitle">{{ artTitle }}</p>
    </div>

    <canvas id="vinesCanvas">
    </canvas>
  </div>

  <transition name="fade">
    <p class="name">
    Hi, my name is <em>Tasha</em>!<br>
    </p>
  </transition>

  <p class="intro">
   I've graduated with a bachelor's degree in computer science and visual arts at the University of Victoria. I have
   a year's worth of experience working as a UX developer/designer. I'm passionate about creating inclusive and dynamic designs.
   I also love to create personal web art projects using mostly three.js and
   blender for 3d modelling.
  </p>

</template>
  
<script>
export default {
  name: 'AboutPage',
  data() {
    return {
      uxTitle: "UX Developer",
      and: "&",
      artTitle: "Artist",
    }
  },
  mounted: function () {
    const canvas = document.getElementById('vinesCanvas');
    const ctx = canvas.getContext('2d');   //context - could also be set to webgl
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    window.addEventListener('resize', function() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;

      ctx.lineCap = 'round';
      ctx.lineWidth = 12;
      ctx.beginPath();
      ctx.strokeStyle = '#6FC18C'
      ctx.moveTo(-3, 650);
      ctx.bezierCurveTo(50, 550, 300, 400, 400, 500);
      ctx.bezierCurveTo(600, 650, 500, 300, 800, 300);
      ctx.bezierCurveTo(900, 300, 900, 200, 1300, 0);
      ctx.stroke();
      
      ctx.lineWidth = 8;
      ctx.beginPath();
      ctx.strokeStyle = '#A9D18E';
      ctx.moveTo(500, -1);
      ctx.bezierCurveTo(500, 200, 900, 200, 1000, 400);
      ctx.bezierCurveTo(1100, 600, 1300, 400, 1550, 300);
      ctx.stroke();

      ctx.lineWidth = 10;
      ctx.beginPath();
      ctx.strokeStyle = '#707070';
      ctx.moveTo(900, -1);
      ctx.bezierCurveTo(300, 400, 900, 800, 1100, 600);
      ctx.bezierCurveTo(1200, 500, 1300, 400, 1550, 700);
      ctx.stroke();
    });


    ctx.lineCap = 'round';
    ctx.lineWidth = 12;
    ctx.beginPath();
    ctx.strokeStyle = '#6FC18C'
    ctx.moveTo(-3, 650);
    ctx.bezierCurveTo(50, 550, 300, 400, 400, 500);
    ctx.bezierCurveTo(600, 650, 500, 300, 800, 300);
    ctx.bezierCurveTo(900, 300, 900, 200, 1300, 0);
    ctx.stroke();
    
    ctx.lineWidth = 8;
    ctx.beginPath();
    ctx.strokeStyle = '#A9D18E';
    ctx.moveTo(500, -1);
    ctx.bezierCurveTo(500, 200, 900, 200, 1000, 400);
    ctx.bezierCurveTo(1100, 600, 1300, 400, 1550, 300);
    ctx.stroke();

    ctx.lineWidth = 10;
    ctx.beginPath();
    ctx.strokeStyle = '#707070';
    ctx.moveTo(900, -1);
    ctx.bezierCurveTo(300, 400, 900, 800, 1100, 600);
    ctx.bezierCurveTo(1200, 500, 1300, 400, 1550, 700);
    ctx.stroke();


    /*function animate() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      
      requestAnimationFrame(animate);
    }

    animate();*/
  }
}



</script>

<style scoped>

.name {
  color:#000000;
  font-weight: 200;
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 40px;
  margin-left: 40px;
  padding-top: 525px;
  margin-block-start: 0px;
}

.name em {
  color:#123800;
}

.intro {
  color:#707070;
  font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  font-size: 30px;
  margin-left: 40px;
  margin-block-start: 0px;
}

.aboutTitle {
  color:#000000;
  font-weight: 200;
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 60px;
  margin-left: 40px;
}

.container {
  position: relative;
  width: 100%;
  height: 200px;
}
.container, canvas, .overlay {
  position: absolute;
}
canvas {
  width: 100%;
  height: 600px;
  z-index: 1;
}
.fade-enter-from {
  opacity: 0;
}

.fade-enter-to {
  opacity: 1;
}

.fade-enter-active {
  transition: all 4s ease;
}

.fade-leave-from {
 opacity: 1;
}

.fade-leave-to {
opacity: 0;
}

.fade-leave-active {
transition: all 4s ease;
}
</style>