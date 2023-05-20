<template>
  <div class="container">
    <div class="row">
      <div class="col-6">
        <p class="aboutTitle">{{ uxTitle }}</p>
        <p class="aboutTitle">{{ and }}</p>
        <p class="aboutTitle">{{ artTitle }}</p>
      </div>
      <div class="col-6">
        <div id="scene-container">
        </div>
      </div>
    </div>
    <div class="row">
      <p class="col-12 name">
        Hi, my name is <em>Tasha</em>!<br>
      </p>
    </div>
    <div class="row">
      <p class="col-12 intro">
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
      camera: null,
      container: null,
      clock: null,
      scene: null,
      mixer: null,
      renderer: null
    }
  },
  methods: {
    init: function() {
      this.container = document.querySelector('#scene-container');

      this.clock = new THREE.Clock();
      this.scene = new THREE.Scene();

      const ambientLight = new THREE.AmbientLight( 0xcccccc, 0.4 );
      this.scene.add( ambientLight );

      const directionalLight = new THREE.DirectionalLight( 0xffffff, 0.8 );
      directionalLight.position.set( 1, 1, 0 ).normalize();
      this.scene.add( directionalLight );

      const fov = 35;
      const aspect = this.container.clientWidth / this.container.clientHeight;
      const near = 0.1;
      const far = 100;

      this.camera = new THREE.PerspectiveCamera(fov, aspect, near, far);

      this.camera.position.set(0, 0, 10);

      var loader = new GLTFLoader();

      loader.load("../assets/bird-metallic1.glb", function(gltf) {
        this.mixer = new THREE.AnimationMixer(gltf.scene);
        this.mixer.clipAction(gltf.animations[0]).play();

        this.scene.add(gltf.scene);
      });

      this.renderer = new THREE.WebGLRenderer();
      this.renderer.setSize(this.container.clientWidth, this.container.clientHeight);
      this.renderer.setPixelRatio(window.devicePixelRatio);
      this.container.append(this.renderer.domElement);
    },
    animate: function() {
      requestAnimationFrame(this.animate);

      const dt = this.clock.getDelta();

      if(this.mixer) {
        this.mixer.update(dt);
      }

      this.renderer.render(this.scene, this.camera);
    }
  },
  mounted() {
    this.init();
    this.animate();
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
}

#scene-container {
  position: absolute;
  width: 200px;
  height: 200px;
  background-color:rgb(100, 138, 108);
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
  height: 100%;
  background: #F4FCED;
  z-index: 0;
}
</style>