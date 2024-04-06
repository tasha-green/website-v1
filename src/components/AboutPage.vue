<template>
  <div class="container">
    <div class="row d-flex flex-wrap pb-4">
      <div class="col-10 col-md-5">
        <p class="aboutTitle">{{ uxTitle }}</p>
        <p class="aboutTitle">{{ and }}</p>
        <p class="aboutTitle">{{ artTitle }}</p>
      </div>
      <div class="col-7 scene">
        <div id="scene-container"></div>
      </div>
    </div>
    <div class="row">
      <p class="col-10 name">
        Hi, my name is <em>Tasha</em>!<br>
      </p>
      
    </div>
    <div class="row">
      <p class="col-10 intro">
        I've recently graduated from the University of Victoria with a bachelor of science in computer science and visual arts. I also have
        a year's worth of experience working as a UX designer. I'm passionate about designing and creating inclusive and responsive designs.
        I also love to create personal web art projects using THREE.js and blender.
      </p>
    </div>
    <div class="row">
      <h2 class="col-10 title">UX Design</h2>
    </div>

    <div class="flex-row card d-flex my-4">
      <div class="col-5 card-image">
        <a href="https://www.ddetailspainting.com/" target="_blank"><img src="/Details-Painting.PNG" alt="Details Painting Logo"></a>
      </div>

      <div class="col-7 ps-3 pt-2">
        <div class="row">
          <div class="col-6">
            <a class="card-title btn btn-link p-0 m-0" href="https://www.ddetailspainting.com/" target="_blank" role="button">Details Painting</a>
          </div>
          <div class="col-6">
            <p class="card-time">May 2023 - July 2023</p>
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

    <div class="flex-row card d-flex my-4">
      <div class="col-5 card-image">
        <a href="https://observablehq.com/d/f8b681d8b2a20dc6" target="_blank"><img class="white_background" src="/d3.PNG" alt="Sunburst photo"></a>
      </div>

      <div class="col-7 ps-3 pt-2">
        <div class="row">
          <div class="col-6">
            <a class="card-title btn btn-link p-0 m-0" href="https://observablehq.com/d/f8b681d8b2a20dc6" target="_blank" role="button">The Effects of the Pandemic on Student's Mental Health</a>
          </div>
          <div class="col-6">
            <p class="card-time">Sept 2022 - Dec 2022</p>
          </div>
        </div>
        <div class="row">
          <div class="col-12">
            <p class="card-body">In a team of two, we created a unique zoomable sunburst chart to show how the pandemic affected the mental health of students across Canada based of different age ranges.
              The project was for a fourth year design course at the University of Victoria. The data we used came from the University of Victoria Dataverse Collection and was
              done in 2020.
            </p>
          </div>
        </div>
      </div>
    </div>

    <div class="flex-row card d-flex my-4">
      <div class="col-5 card-image">
        <a href="https://www.pilatesonthelake.ca/" target="_blank"><img class="white_background" src="/Pilates.png" alt="Pilates Logo"></a>
      </div>

      <div class="col-7 ps-3 pt-2">
        <div class="row">
          <div class="col-6">
            <a class="card-title btn btn-link p-0 m-0" href="https://www.pilatesonthelake.ca/" target="_blank" role="button">Pilates on The Lake</a>
          </div>
          <div class="col-6">
            <p class="card-time">May 2020</p>
          </div>
        </div>
        <div class="row">
          <div class="col-12">
            <p class="card-body">Pilates on The Lake asked for a new logo for their new website. Using adobe Illustrator,
              I tried to create designs based off of the client's favourite pilates poses. I also made sure to be mindful of the website's colour palette
              during the iterative design process. I used a tool called Colour Space which generates different types of colour palettes based off of a single colour.  
            </p>
          </div>
        </div>
      </div>
    </div>

    <div class="flex-row card d-flex my-4">
      <div class="col-5 card-image">
        <a href="https://www.usnr.com/en/page/home" target="_blank"><img class="white_background" src="/USNR.png" alt="USNR Logo"></a>
      </div>

      <div class="col-7 ps-3 pt-2">
        <div class="row">
          <div class="col-6">
            <a class="card-title btn btn-link p-0 m-0" href="https://www.usnr.com/en/page/home" target="_blank" role="button">USNR</a>
          </div>
          <div class="col-6">
            <p class="card-time mb-0">May 2018 - Aug 2018</p>
            <p class="card-time">Dec 2018 - Aug 2019</p>
          </div>
        </div>
        <div class="row">
          <div class="col-12">
            <p class="card-body">I was hired as a coop student for USNR, which is an international sawmill company that strives to create efficient sawmill machines.
              I worked as part of a small team of front-end developers and designers that were in the process of redesigning and updating the software 
              that controlled the different sawmill machines.  We worked on the overall themes, icons, fonts & spacing, main menu and pages associated with the trimmer.
              I also helped test and fix small bugs.
            </p>
          </div>
        </div>
      </div>
    </div>

      <div class="flex-row card d-flex my-4">
        <div class="col-5 card-image">
          <a href="https://www.communitystories.ca/v2/paleontology-vancouver-islnd_paleontologie-ile-vancouver/" target="_blank"><img class="white_background" src="/QB_Museum.png" alt="Qualicum Beach Museum Logo"></a>
        </div>

        <div class="col-7 ps-3 pt-2">
          <div class="row">
            <div class="col-6">
              <a class="card-title btn btn-link p-0 m-0" href="https://www.communitystories.ca/v2/paleontology-vancouver-islnd_paleontologie-ile-vancouver/" target="_blank" role="button">Qualicum Beach Museum</a>
            </div>
            <div class="col-6">
              <p class="card-time">June 2017 - Aug 2017</p>
            </div>
          </div>
          <div class="row">
            <div class="col-12">
              <p class="card-body">I worked with a small team to create the Virtual Museum Project. 
                My role was to use WordPress to add the Qualicum Beach paleontology stories to the project. 
                I primarily used WordPress’s HTML editor.
              </p>
            </div>
          </div>
        </div>
      
      </div>

    <div class="row">
      <h2 class="col-10 title">Digital Art</h2>
    </div>

    <div class="flex-row card d-flex my-4">
      <div class="col-5 card-image">
        <img src="/Birds.PNG" alt="Bird blender">
      </div>

      <div class="col-7 ps-3 pt-2">
        <div class="row">
          <div class="col-6">
            <h5 class="card-title">Flocking of a Complex 3d Model</h5>
          </div>
          <div class="col-6">
            <p class="card-time">Jan 2023 - April 2023</p>
          </div>
        </div>
        <div class="row">
          <div class="col-12">
            <p class="card-body">This was a semester long graphics project for a fourth year class at the university of Victoria. 
              The project was built using THREE.js and blender. It was divided into several parts: modelling, character control, collision handling and a flocking simulation.
              The flocking animation was a leader agent-based mathematical model. While it does take light inspiration from the boids algorithm, it adds layers
              of complexity to better model the behaviour of birds. There are three steering forces: repulsion, alignment and attraction. Gravity is also taken into account</p>
          </div>
        </div>
      </div>
    </div>


    <div class="flex-row card d-flex my-4">
      <div class="col-5 card-image">
        <a href="https://codesandbox.io/s/connections-32kwp" target="_blank"><img src="/connections-1.PNG" alt="Connections image sample"></a>
      </div>

      <div class="col-7 ps-3 pt-2">
        <div class="row">
          <div class="col-6">
            <a class="card-title btn btn-link p-0 m-0" href="https://codesandbox.io/s/connections-32kwp" target="_blank" role="button">Connections</a>
          </div>
          <div class="col-6">
            <p class="card-time">Sept 2020 - April 2021</p>
          </div>
        </div>
        <div class="row">
          <div class="col-12">
            <p class="card-body">Connections was a THREE.js art piece created for my fourth year intensive arts course at the University of Victoria. It was an eight month long abstract piece that
            explores mood swings. I hoped to express the internal chaos that can come with hypomania, depression and the mixed episodes of bipolar II. 
            It can be very difficult to convey the realities of mental illnesses when so much of it is internal so I dedicated my fourth year art courses to learning
            and creating art about various mental illnesses.
            </p>
          </div>
        </div>
      </div>
    </div>

    <div class="flex-row card d-flex my-4">
      <div class="col-5 card-image">
        <a href="https://codesandbox.io/s/interactive-audio-how-do-you-feel-3i5zr" target="_blank"><img src="/polar.PNG" alt="Details Painting Logo"></a>
      </div>

      <div class="col-7 ps-3 pt-2">
        <div class="row">
          <div class="col-6">
            <a class="card-title btn btn-link p-0 m-0" href="https://codesandbox.io/s/interactive-audio-how-do-you-feel-3i5zr" target="_blank" role="button">How do you feel?</a>
          </div>
          <div class="col-6">
            <p class="card-time">Sept 2020</p>
          </div>
        </div>
        <div class="row">
          <div class="col-12">
            <p class="card-body">This interactive audio piece was a month long project to convey social anxiety. It was made using THREE.js.
              The audio is using stereo so, headphones are preferred. This was my first interactive piece.
            </p> 
          </div>
        </div>
      </div>
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
        //model.position.set(0, -1.75, 0);
        model.scale.set(0.4, 0.4, 0.4);
        scene.add(gltf.scene);
      });

      //camera.position.set(0, 0, 20);
      //camera.lookAt(0, 0, 0);

      animate();
    }


    function animate() {
      requestAnimationFrame(animate);

     if(model) {
      model.rotation.y += 0.005;

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
  height: -webkit-fill-available;
  object-fit: cover;
  border-top-left-radius: 15px;
  border-bottom-left-radius: 15px;
}

.white_background {
  object-fit: contain;
}

.card-title {
  font-family: 'Courier New', Courier, monospace;
  font-size: 20px;
  text-align: left;
}

h2 {
  margin-left: 40px;
}
.card-time {
  font-weight: lighter;
  font-family: 'Courier New', Courier, monospace;
  text-align: right;
  margin-right: 4%;
}

.card-body {
  padding: 0%;
  margin-right: 4%;
  font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;

}

@media (max-width: 770px) {
  .scene {
    display: none;
  }
}


</style>