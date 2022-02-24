<template>
  <div class="container">

<hr class="mt-5 mb-5" />
    <div class="d-flex JS">
      <div>
        <listofcomp  @comp="callcomp"/>
      </div>
    <div class="componentWidth">
      <h1 class="text-center"><strong>پسورد تصادفی</strong></h1>
      <div class="mt-3 text-center" style="min-height: 120px">
        <div class="card card-body" style="width: 100%">
          <p>{{ result }}</p>
        </div>
      </div>
     <div class="slidecontainer mt-1">
        <input
          type="range"
          min="1"
          max="20"
          v-model="length"
          class="slider"
          id="myRange"
        />
      </div> 
      <div class="text-end">
        <div class="mt-2 d-flex spc">
          <div>
            <input
              class="inputLength"
              type="number"
              id="length"
              min="4"
              max="20"
              v-model="length"
            />
          </div>
          <label class="lengthLabel">طول پسورد</label>
        </div>

        <div class="mt-2">
          <label> شامل حروف کوچک بشود</label>
          <input
            type="checkbox"
            class="form-check-input bg-success"
            checked
            v-model="checkedLowercase"
          />
        </div>
        <div class="mt-2">
          <label> شامل حروف بزرگ بشود</label>
          <input
            type="checkbox"
            class="form-check-input bg-success"
            checked
            v-model="checkedUppercase"
          />
        </div>
        <div class="mt-2">
          <label>شامل عدد بشود</label>
          <input
            type="checkbox"
            class="form-check-input bg-success"
            checked
            v-model="checkedNumbers"
          />
        </div>
        <div class="mt2">
          <label> شامل نشانه ها بشود</label>
          <input
            type="checkbox"
            class="form-check-input bg-success"
            checked
            v-model="checkedSymbols"
          />
        </div>
      </div>
      <div class="mt-3">
        <button
          class="btnM col-12 text-center text-light"
          type="button"
          id="generate"
          @click="Generate"
        >
          تایید
        </button>
      </div>
    </div>
    </div>
  </div>
</template>
<script>
import listofcomp from './listofcomp.vue';
export default {
  name: "passwordGenerator",
  data: function () {
    return {
      checkedLowercase: true,
      checkedUppercase: true,
      checkedNumbers: true,
      checkedSymbols: true,
      length: "",
      result: "پسورد",
      chechedArray: [],

      test:'',
    };
  },
  components: {
    listofcomp,
  },
  methods: {
    Generate() {
      this.result = "";
      if (
        this.checkedLowercase == false &&
        this.checkedUppercase == false &&
        this.checkedNumbers == false &&
        this.checkedSymbols == false
      )
        this.result = "لطفا یکی از گزینه ها رو انتخاب کنید";
      else if (this.length == "") this.result = "لطفا طول رمز را تعیین کنید";
      else {
        for (let i = this.length; i > 0; i--) {
          this.CheckFunctionArray();
          this.result +=
            this.chechedArray[
              Math.floor(Math.random() * this.chechedArray.length)
            ];
        }
      }
    },
    //mount checkArray
    CheckFunctionArray() {
      this.chechedArray = [];
      if (this.checkedLowercase) this.chechedArray.push(this.getRandomLower());
      if (this.checkedUppercase) this.chechedArray.push(this.getRandomUpper());
      if (this.checkedNumbers) this.chechedArray.push(this.getRandomNumber());
      if (this.checkedSymbols) this.chechedArray.push(this.getRandomSymbol());
    },
    getRandomNumber() {
      return String.fromCharCode(Math.floor(Math.random() * 10) + 48);
    },
    // Generator functions
    getRandomLower() {
      return String.fromCharCode(Math.floor(Math.random() * 26) + 97);
    },
    getRandomUpper() {
      return String.fromCharCode(Math.floor(Math.random() * 26) + 65);
    },
    getRandomSymbol() {
      // symbol = "!@$%^&*()_+=-*|/`~<>,.?:;";
      const symbol = ["!", "@", "#", "$", "%", "^", "&", "*", "?"];
      return symbol[Math.floor(Math.random() * symbol.length)];
    },
     callcomp(x){
        this.$emit('comp',x);
      }
  },
  
};
</script>
<style scoped>
.spc {
  display: flex;
  justify-content: space-between;
}
</style>
