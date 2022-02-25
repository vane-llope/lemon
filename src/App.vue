<template>
  <div>
   <nav class="d-flex JS mt-4 navM" >
      <div class="d-flex ">
       <a class="navbar-brand brand"><img src="./assets/icons/lemon.png"></a>
       <a class="nav-link active "   @click="choosen='mainpage'" href="#"><strong>Home</strong></a>
       <a class="nav-link active "   href="#"><strong>About</strong></a>
</div>
<div class="d-flex" v-bind:class="{ darkmood }" >
        <button class="btnM" @click="myFunction()">mode</button>
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
    },
   myFunction() {
   var element = document.body;
   element.classList.toggle("dark-mode");
}
  },
 
}
</script>

<style>
@import "./assets/style/style.css";

</style>
