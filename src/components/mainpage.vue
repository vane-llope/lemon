<template>
    <div>
 <!--intro-->
 <div class="container introimg">
   <img  src="../assets/images/intro.jpg" alt="">
 </div>
<div class="container intro">
  
  <h1 class="container text-center">این
    <span class="web">وبسایت</span>
     با هدف ارائه محاسبات و ابزارهای آنلاین شروع به کار کرده است  ابزارهایی که هر جایی ممکن است مورد نیاز باشد 
     </h1>
</div>
<!--services-->
<div class="container mt-4 text-center">
  <hr>
  <h2 class="text-center mt-5 mb-5" >ابزار ها</h2>
  <div class="container ">
      <!--row1-->
       <div class="row mt-5">
    <div class="col-md mb-5 cmpnt darkothercopm" @click="component='numToLetter'; callcomp();" >
       <img src="../assets/icons/NL.png" alt="">
      <p>تبدیل عدد به حروف </p>
    </div>
    <div class="col-md  mb-5 cmpnt darkothercopm"  @click="component='passwordGenerator'; callcomp();">
      <img src="../assets/icons/lock.png" alt="">
     <p>پسورد تصادفی</p>
    </div>
    <div class="col-md  mb-5 cmpnt darkothercopm"  @click="component='melicode'; callcomp();">
     <img src="../assets/icons/identity.png" alt="">
     <p>صحت کد ملی</p>
    </div>
     <div class="col-md  mb-5 cmpnt darkothercopm" @click="component='engToPer'; callcomp();">
       <img src="../assets/icons/EtP.png" alt="">
      <p>تبدیل عدد فارسی به انگلیسی</p>
    </div>
  </div>
  <!--row2-->
  <div class="row mt-5">
    <!--<div class="col-md mb-5 cmpnt"  @click="component='birth'; callcomp();">
       <img src="../assets/icons/bearth.png" alt="">
      <p>محاسبه ی سن</p>
      <p  class="cexplain">به میلادی شمسی و قمری</p>
    </div>-->
    <div class="col-md  mb-5 cmpnt darkothercopm"  @click="component='date'; callcomp();">
      <img src="../assets/icons/Calendar.png" alt="">
     <p> تاریخ امروز</p>
     <p  class="cexplain">به میلادی شمسی و قمری</p>
    </div>
     <div class="col-md  mb-5 cmpnt darkothercopm"  @click="component='percentage'; callcomp();">
     <img src="../assets/icons/perspective.png" alt="">
     <p>محاسبه ی درصد</p>
      <p  class="cexplain"> محاسبه ی افزایش یا کاهش درصد حقوق، قیمت و غیره </p>
    </div>
    <div class="col-md  mb-5 cmpnt darkothercopm "  @click="component='MBI'; callcomp();">
     <img src="../assets/icons/wight.png" alt="">
     <p>  شاخص توده ی بدنی</p>
      <p  class="cexplain">MBI</p>
    </div>
     <div class="col-md  mb-5 cmpnt darkothercopm"  @click="component='typoStuff'; callcomp();">
       <img src="../assets/icons/typo.png" alt="" >
      <p>شمارش تعداد کاراکتر,کلمه و جمله</p>
      <p  class="cexplain"></p>
    </div>
  </div>
  </div>
  <div class="container comment d-flex">
      <img src="../assets/images/comment.png" alt="">  
    <div>
      <img class=" icon" src="../assets/icons/message.png" alt="">
    <p class="text-end " > شما می توانید برای کمک به ما جهت بهتر شدن امکانات و ابزار های آنلاین 
     یا افزودن ابزار های جدید ویا موارد دیگر
      
      نظرات، پیشنهادات و انتقادات خود را با کلیک روی این دکمه برای ما ارسال کنید</p>
      <!-- Button trigger modal -->
<button type="button" class="btnM mt-5" data-bs-toggle="modal" data-bs-target="#exampleModal">
  نظرات شما
</button>

  </div>
  </div>
  
</div>
<!-- Modal 
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">

        <div class="form-floating mt-3 ">
  <input type="text" class="form-control" id="floatingPassword" >
  <label for="floatingInput">نام</label>
</div>
        <div class="form-floating mt-3 mb-3 ">
  <input type="email" class="form-control " id="floatingInput" placeholder="name@example.com">
  <label  for="floatingInput">ایمیل</label>
</div>
<textarea
      class="form-control text-center"
      style="width:100%; height:100px"
      type=""
      placeholder="نظر خود را وارد کنید"
      v-model="text"
    />


      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>-->
    
    </div>
</template>

<script>
export default {
    name:'mainpage',
    data() {
      return {
        component:'',
      }
    },
    methods: {
      callcomp(){
        this.$emit('comp',this.component);
      }
     
    },
    mounted() {
      console.log(this.image)
    },
}
</script>