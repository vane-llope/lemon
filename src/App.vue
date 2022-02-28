<template>
  <div>
   <nav class="d-flex JS mt-4 navM" >
      <div class="d-flex ">
       <a class="navbar-brand brand"><img src="./assets/icons/lemon.png"></a>
       <a class="nav-link active "   @click="choosen='mainpage'" href="#"><strong>Home</strong></a>
       <!-- Button trigger modal -->
<a type="button" class="nav-link active" data-bs-toggle="modal" data-bs-target="#exampleModal"><strong>About</strong></a>
</div>
<div class=" btnMood " v-bind:class="{ darkmood }" >
        <button class=" btn " @click="myFunction()"><img src="./assets/icons/Sun.png" alt=""></button>
      </div>
    </nav>
<!--component-->
<component @comp="call"  v-bind:is="choosen"></component>
 <!--footer-->
 <ending />
<!-- Modal-->
<div class="modal fade " id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modalM ">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">درباره ی ما</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body text-end">
         <p>
          بخش های متنوع این وبسایت شامل تولید پسورد تصادفی,بررسی صحت کد ملی,تبدیل عدد فارسی و انکلیسی,تبدیل عدد به حروف,شمارش کاراکتر,کلمه و جمله,محاسبه ی شاخص توده ی بدنی و نمایش تاریخ روز میباشد
        </p>
        <p>
          این وبسایت با هدف ارائه محاسبات و ابزارهای آنلاین شروع به کار کرده است ابزارهایی که هر جایی ممکن است مورد نیاز باشد در این سایت میتوانید انواع محاسبات را به سهولت انجام دهید
        </p>
      </div>
      <div class="modal-footer">
        <button type="button" style="width:70px" class="btnM " data-bs-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
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
