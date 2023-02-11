<template>
  <div class="container h-100 mt-3 mb-5">
    <div class="row outline mb-0">
      <div class="col-md-3 bg-grey outline nb-left" style="border-bottom:none">
        <div class="row ml-n3">
          <div class="col-md-12 pt-2 pb-2 d-flex flex-column align-items-center text-center">
            <div class="triangle mb-3"></div>
            <h5>{{ name }}</h5>
          </div>
        </div>
        <div class="row outline ml-n3 nb-right">
          <div class="col-12 text-center pt-2"><h5 class="text-center">CONTACT</h5></div>
        </div>
        <div class="row outline ml-n3 nb-right">
          <div class="col-12 pl-2 py-2 pr-0 bg-white"><i class="far fa-envelope mr-1"></i> 
            <a :href="`mailto:${email}`">{{ email }}</a>
          </div>
        </div>
        <div class="row outline ml-n3 nb-right">
          <div class="col-12 pl-2 py-2 pr-0 bg-white"><i class="fas fa-phone mr-1"></i> {{ phone }}</div>
        </div>
        <div class="row outline ml-n3 nb-right">
          <div class="col-12 pl-2 py-2 pr-0 bg-white"><i class="far fa-address-card mr-1"></i> {{ address }}</div>
        </div>
        <div class="row outline ml-n3 nb-right">
          <div class="col-12 text-center pt-2"><h5 class="text-center">SKILLS</h5></div>
        </div>
        <div
          class="row ml-n3 outline nb-right"
        >
          <div
            v-for="skill in skills"
            :key="skill"
            class="col-12 pl-0 py-0 pr-0 pt-1 skill"
          >
            <div style="height: 25px; position:relative; width:100%" class="bg-white">
              <div 
                style="position:absolute; height: 100%;"
                class="pbar"
                :style="{'width': `${skill.level*100}%`}">
              </div>
              <div
                style="position:absolute; z-index:1; width: 100%"
                class="text-left pl-2 pt-0">
                {{ skill.name }}
              </div>
            </div>
          </div>
        </div>
        <div class="row outline ml-n3 nb-right">
          <div class="col-12 text-center pt-2"><h5 class="text-center">LANGUAGES</h5></div>
        </div>
        <div
          class="row ml-n3 outline nb-right " style="border-bottom:none"
        >
          <div
            v-for="language in languages"
            :key="language"
            class="col-12 pl-0 py-0 pr-0 bg-white mt-1 skill"
          >
            <div style="height: 25px; position:relative; width:100%">
              <div 
                style="position:absolute; height: 100%;"
                class="pbar"
                :style="{'width': `${language.level*100}%`}">
              </div>
              <div
                style="position:absolute; z-index:1; width: 100%"
                class="text-left pl-2 pt-0">
                {{ language.name }}
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-9 pl-4 pt-1 pr-2">
        <div class="row d-block">
          <h4>Highlights</h4>
          <p
            v-for="highlight in highlights"
            :key="highlight"
          >{{highlight}}</p>
        </div>
        <div class="row pb-3"></div>
        <div class="row">
          <div class="row m-0"><h4>Experience</h4></div>
          <span
            v-for="item in experience"
              :key="item"
              class="experience-item"
          >
            <div class="row">
              <div class="col-5 blue"><strong>{{ item.company }}</strong></div> 
              <div class="col-4"><strong>{{ item.title }}</strong></div>
              <div class="col-3"><strong>{{ item.dates }}</strong></div>
            </div>
            <div class="row m-0">
              <p class="col-12 p-0" v-for="detail in item.details" :key="detail">
                {{ detail }}
              </p>
            </div>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import data from './cv-data-example.yml';

export default {
  name: "App",
  data: () => data,
};
</script>

<style>
a {
  color: inherit;
}
.skill:last-child {
  margin-bottom:4px;
}
:root {
  --main-color: #3168b8;
  --bar-color: #bdd9fbc8;
}
.nb-left {
  border-left: none !important;
}
.nb-right {
  border-right: none !important;
}
.pbar {
  background-color: var(--bar-color);
  border:none;
}
.bg-grey {
  background-color: #f6f7f7;
}
p {
  margin-top: 3px;
  margin-bottom:0;
  clear:both;
}
.experience-item {
  margin-bottom: 20px;
}
* {
  font-family: "Open Sans", sans-serif;
}
h4, h5 {
  color: var(--main-color);
}
.os {
  font-family: "Open Sans", sans-serif;
}
.outline {
  border: 1px solid #ccc;
  border-collapse: collapse;
  margin-top: -1px;
}
.thin {
  font-weight: 350;
}
.square{
  width: 100px;
  height: 100px;
  background-color: var(--main-color);
}
.triangle {
  width: 0; 
  height: 0; 
  border-top: 100px solid transparent;  
  border-right: 100px solid var(--main-color);
}
.blue {
  color: var(--main-color);
}
</style>
