
<template>
  <div class="container">
    <hr class="mt-5 mb-5" />
    <div class="d-flex JS">
      <div>
        <listofcomp @comp="callcomp" />
      </div>
      <div class="componentWidth">
          <h1 class="text-center mb-3" style="font-size:22px">محاسبه ی افزایش یا کاهش درصد حقوق، قیمت و غیره</h1>
        <div class="form-floating mb-3">
  <input type="text" class="form-control" v-model="percent" id="floatingInput" >
  <label for="floatingInput"> ٪ درصد تغییر </label>
</div>

 <div class="form-floating mb-3">
  <input type="text" class="form-control" v-model="num" id="floatingInput" >
  <label for="floatingInput">عدد</label>
</div>

<div class="mt-4 mb-3">
            <button
              class="btnM col-12 text-center text-light"
              type="button"
              @click="calculate"
            >
              تایید
            </button>
          </div>
<div class="d-flex JS">
<div class="mt-3 text-center" >
          <div class="card card-body" style="width: 100%">
              <p class="text-center"> نتیجه ی افزایش درصد</p>
            <p>{{ inc }}</p>
          </div>
        </div>

        <div class="mt-3 text-center" >
          <div class="card card-body" style="width: 100%">
              <p class="text-center"> نتیجه ی کاهش درصد</p>
            <p>{{ dec }}</p>
          </div>
        </div>

<div class="mt-3 text-center" >
          <div class="card card-body" style="width: 100%">
              <p class="text-center"> میزان تغییر</p>
            <p>{{ change }}</p>
          </div>
        </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import listofcomp from "./listofcomp.vue";
export default {
  name: "percentage",
  data() {
      return {
          num:'',
          percent:'',
          inc:'',
          dec:'',
          change:''
          
      }
  },
  components: {
    listofcomp,
  },
  methods: {
    callcomp(x) {
      this.$emit("comp", x);
    },
     calculate(){
         this.percent=parseFloat(this.percent/100);
        this.change=parseFloat(this.num)*parseFloat(this.percent);
        this.inc=parseFloat(this.num)+parseFloat(this.change);
        this.dec=parseFloat(this.num)-parseFloat(this.change);
      }
  },
};
</script>