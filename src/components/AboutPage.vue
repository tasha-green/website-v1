<template>
  <div class="container">
    <div class="row pb-4">
      <div class="col-lg-5">
        <p class="aboutTitle">{{ uxTitle }}</p>
        <p class="aboutTitle">{{ and }}</p>
        <p class="aboutTitle">{{ artTitle }}</p>
      </div>
      <div class="col-lg-7 scene">
        <div id="scene-container">
        </div>
      </div>
    </div>
    <div class="row">
      <p class="col-lg-12 name">
        Hi, my name is <em>Tasha</em>!<br>
      </p>
    </div>
    <div class="row">
      <p class="col-lg-12 intro">
        I've graduated with a bachelor's degree in computer science and visual arts at the University of Victoria. I have
        a years worth of experience working as a UX developer/designer. I'm passionate about creating inclusive and responsive designs.
        I also love to create personal web art projects using mostly three.js and blender for 3d modelling.
      </p>
    </div>
  </div>

</template>
  
<script>
import * as THREE from "../vendor/three/build/three.module.js";
import { GLTFLoader } from "../vendor/three/examples/GLTFLoader.js"

export default {
  name: 'AboutPage',
  data() {
    return {
      uxTitle: "UX Developer",
      and: "&",
      artTitle: "Artist",
    }
  },
  mounted: function() {

    let camera, container, clock, renderer, mixer, scene, loader;

    init();
    animate();

    function init() {
      scene = new THREE.Scene();
      scene.background = new THREE.Color(0xF4FCED);

      clock = new THREE.Clock();

      renderer = new THREE.WebGLRenderer();

      container = document.querySelector('#scene-container');

      /*const ambientLight = new THREE.AmbientLight( 0xffffff, 0.9 );
      scene.add( ambientLight );*/

      /*const light = new THREE.PointLight(0xff0000, 1, 100);
      light.position.set(20, 20, 5);
      scene.add(light);*/

      const fov = 12;
      const aspect = container.clientWidth / container.clientHeight;
      const near = 0.1;
      const far = 150;

      camera = new THREE.PerspectiveCamera(fov, aspect, near, far);

      camera.position.set(0, 2, 20);

      loader = new GLTFLoader();

      loader.load("/tree.glb", function(gltf) {
        gltf.scene.position.set(-0.1, -0.5, 0);
        gltf.scene.scale.set(0.55, 0.55, 0.55);
        //mixer = new THREE.AnimationMixer(gltf.scene);
        //mixer.clipAction(gltf.animations[0]).play();

        scene.add(gltf.scene);
      });

      renderer.setSize(container.clientWidth, container.clientHeight);
      renderer.setPixelRatio(window.devicePixelRatio);
      container.append(renderer.domElement);
    }

    function animate() {
      requestAnimationFrame(animate);

      const dt = clock.getDelta();

      if(mixer) {
        mixer.update(dt);
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
</style>