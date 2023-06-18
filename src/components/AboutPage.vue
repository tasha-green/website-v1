<template>
  <div class="container">
    <div class="row pb-4">
      <div class="col-lg-5">
        <p class="aboutTitle">{{ uxTitle }}</p>
        <p class="aboutTitle">{{ and }}</p>
        <p class="aboutTitle">{{ artTitle }}</p>
      </div>
      <div class="col-lg-7 scene">
        <div id="scene-container"></div>
      </div>
    </div>
    <div class="row">
      <p class="col-lg-12 name">
        Hi, my name is <em>Tasha</em>!<br>
      </p>
    </div>
    <div class="row">
      <p class="col-lg-12 intro">
        I've recently graduated from the University of Victoria with a bachelor of science in computer science and visual arts. I also have
        a years worth of experience working as a UX designer. I'm passionate about designing and creating inclusive and responsive designs.
        I also love to create personal web art projects using three.js and blender.
      </p>
    </div>
    <div class="row">
      <h2 class="col-10 title">UX Design</h2>
    </div>
    <div class="flex-row card d-flex my-4">
      <div class="col-5 card-image">
        <img src="/Details-Painting.PNG" alt="Details Painting Logo">
      </div>

      <div class="col-7 ps-3 pt-2">
        <div class="row">
          <div class="col-8">
            <h5 clas="card-title">Details Painting</h5>
          </div>
          <div class="col-4">
            <p class="card-time">May 2023 - Current</p>
          </div>
        </div>
        <div class="row">
          <div class="col-12">
            <p class="card-body">Details Painting is a small locally-owned painting business looking to upgrade their website.
              For this project, we're using angular with bootstrap. I'm responsible for building the individual pages as well 
              as designing the services, quote, diy and courses pages.</p>
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      <h2 class="col-10 title">Digital Art</h2>
    </div>
  </div>

</template>
  
<script>
import * as THREE from "../vendor/three/build/three.module.js";
import { GLTFLoader } from "../vendor/three/examples/GLTFLoader.js"
import { DRACOLoader } from "../vendor/three/examples/DRACOLoader.js";
import { RoomEnvironment} from "../vendor/three/examples/RoomEnvironment.js";

export default {
  name: 'AboutPage',
  data() {
    return {
      uxTitle: "UX Designer",
      and: "&",
      artTitle: "Artist",
    }
  },
  mounted: function() {

    let camera, container, renderer, scene, loader;

    let model;

    init();
    animate();

    function init() {
      container = document.querySelector('#scene-container');

      renderer = new THREE.WebGLRenderer({antialias: true});
      renderer.setSize(container.clientWidth, container.clientHeight);
      renderer.setPixelRatio(window.devicePixelRatio);
      container.append(renderer.domElement);

      scene = new THREE.Scene();
      scene.background = new THREE.Color(0xF4FCED);
      
      const pmremGenerator = new THREE.PMREMGenerator(renderer);

      scene.environment = pmremGenerator.fromScene( new RoomEnvironment(), 0.04).texture;

      const fov = 12;
      const aspect = container.clientWidth / container.clientHeight;
      const near = 0.1;
      const far = 150;

      camera = new THREE.PerspectiveCamera(fov, aspect, near, far);

      camera.position.set(0, 2, 20);

      const dracoLoader = new DRACOLoader();
      dracoLoader.setDecoderPath('/gltf/');

      loader = new GLTFLoader();
      loader.setDRACOLoader(dracoLoader);
      loader.load("/tree.glb", function(gltf) {
        model = gltf.scene;
        model.position.set(0, 0, 0);
        model.scale.set(0.4, 0.4, 0.4);
        scene.add(gltf.scene);
      });

  

      animate();
    }

    function animate() {
      requestAnimationFrame(animate);


     if(model) {
      model.rotation.y += 0.01;

      if(model.rotation.y >= Math.PI * 2) {
        model.rotation.y = 0;
      }
     }

      renderer.render(scene, camera);
    }
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
  margin-block-start: 0px;
  height: 100%;
}

.scene {
  height: 460px;
}

#scene-container {
  position: absolute;
  width: 520px;
  height: 460px;
  color: #F4FCED;
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
  padding: 0px;
  width: 100%;
  height: 100%;
  background: #F4FCED;
  z-index: 0;
}

.card {
  box-shadow: 5px 5px 5px lightgrey;
  border: none;
  border-radius: 15px;
  margin-left: 40px
}

img {
  width: 100%;
  border-top-left-radius: 15px;
  border-bottom-left-radius: 15px;
}

h5 {
  font-family: 'Courier New', Courier, monospace;
}

h2 {
  margin-left: 40px;
}
.card-time {
  font-weight: lighter;
  font-family: 'Courier New', Courier, monospace;
}

.card-body {
  padding: 0%;
  margin: 0%;
  font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>