<template>
<div class="container">
  <hr class="mt-5 mb-5" />
    <div class="d-flex JS">
  <div>
         <listofcomp  @comp="callcomp" />
      </div>
    <div class="componentWidth">
    <h1 class="text-center">تبدیل عدد فارسی و انگلیسی</h1>
    <input
      class="form-control text-center mt-5 darkothercopm"
      type="text"
      placeholder="عدد در این قسمت وارد شود"
      v-model="numberPE"
    />
    <div></div>
    <div class="mt-4">
      <button
        class="btnM col-12 text-center text-light"
        type="button"
        @click="assign"
      >
        تایید
      </button>
    </div>
    <div class="mt-3 text-center" style="min-height: 120px">
      <div class="card card-body darkothercopm" style="width: 100%">
        <p>{{ resultPE }}</p>
      </div>
    </div>
  </div>
  </div>
</div>
</template>
<script>
import listofcomp from './listofcomp.vue'
export default {
  name: "engToPer",
  data: function () {
    return {
      numberPE: "",
      resultPE: "لطفا عدد مورد نظر را وارد و تایید کنید",
      pn: ["۰", "۱", "۲", "۳", "۴", "۵", "۶", "۷", "۸", "۹"],
      eng: ["0", "1", "2", "3", "4", "5", "6", "7", "8", "9"],
    };
  },
  components: {
    listofcomp,
  },
  methods: {
    assign() {
      let temp = "";
      for (let i = 0; i < 10; i++) {
        if (this.numberPE[0].includes(this.pn[i])) {
          temp = "pn";
          break;
        }
      }
      if (temp == "pn") this.PnToEng();
      else this.EngToper();
    },
    PnToEng() {
      let temp = "";
      for (let j = 0; j < this.numberPE.length; j++) {
        for (let i = 0; i < 10; i++) {
          if (this.numberPE[j].includes(this.pn[i])) {
            temp += this.eng[i];
            break;
          }
        }
      }
      this.resultPE = temp;
    },
    EngToper() {
      let temp = "";
      for (let j = 0; j < this.numberPE.length; j++) {
        for (let i = 0; i < 10; i++) {
          if (this.numberPE[j].includes(this.eng[i])) {
            temp += this.pn[i];
            break;
          }
        }
      }
      this.resultPE = temp;
    },
      callcomp(x){
        this.$emit('comp',x);
      }
  },
};
</script>
