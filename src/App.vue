<template>
  <div>
   <nav class="navbar navbar-expand-lg navbar-light ">
  <div class="container-fluid mt-3">
    <a class="navbar-brand brand"><img src="./assets/icons/lemon.png" style="width:42px;"></a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item" @click=" choosen='mainpage'">
          <a class="nav-link active" style="padding-left:35px;" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
         <a class="nav-link active" style="padding-left:35px;"  aria-current="page" href="#">about</a>
        </li>
      </ul>
      <div class="d-flex" v-bind:class="{ darkmood }" >
        <button class="btnM"  type="submit">switch</button>
      </div>
    </div>
  </div>
</nav>
<!--component-->
<component @comp="call"  v-bind:is="choosen"></component>
 <!--footer-->
 <ending />
  </div>
</template>

<script>
import mainpage from './components/mainpage.vue';
//components
import numToLetter from './components/numToLetter.vue';
import melicode from './components/melicode.vue';
import engToPer from './components/EtoP.vue';
import passwordGenerator from './components/passwordGenerator.vue';
import typoStuff from './components/typoStuff.vue';
import MBI from "./components/MBI.vue";
import percentage from './components/percentage.vue';
import date from './components/date.vue'
//footer
import ending from './components/ending.vue';


export default {
  name: 'App',
  components: {
   mainpage,
   ending,
   numToLetter,
   melicode,
   engToPer,
   passwordGenerator,
   MBI,
   typoStuff, 
   percentage,
   date,
   
  },
  data() {
    return {
      choosen:'mainpage',
    }
  },
  methods: {
    call(x){
      this.choosen=x;
    }
  },
}
</script>

<style>
@import "./assets/style/style.css";

</style>
