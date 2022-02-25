<template>
  <div class="container">
    <hr class="mt-5 mb-5" />
    <div class="d-flex JS">
      <div>
         <listofcomp  @comp="callcomp" />
      </div>

      <div class="componentWidth">
        <h1 class="text-center">تبدیل عدد به حروف</h1>
        <input
          class="form-control text-center mt-4 darkothercopm"
          type="text"
          placeholder="عدد را وارد کنید"
          v-model="number"
        />
        <div>
          <div class="mt-3">
            <button
              class="btnM col-12 text-center text-light mt-2"
              type="button"
              @click="changeNumber"
            >
              تایید
            </button>
          </div>

          <div class="mt-3 text-center" style="min-height: 120px darkothercopm">
            <div class="card card-body darkothercopm" style="width: 100%">
              <p>{{ resultN }}</p>
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
  name: "numToLetter",
  data: function () {
    return {
      resultN: "این تبدیل تا 12 رقم را در بر میگیرد",
      number: "",
      constLetters: [
        ["صفر", "یک", "دو", "سه", "چهار", "پنج", "شش", "هفت", "هشت", "نه"],
        [
          "ده",
          "یازده",
          "دوازده",
          "سیزده",
          "چهارده",
          "پانزده",
          "شانزده",
          "هفده",
          "هجده",
          "نوزده",
        ],
        ["", "", "بیست", "سی", "چهل", "پنجاه", "شصت", "هفتاد", "هشتاد", "نود"],
        [
          "",
          "یکصد",
          "دویست",
          "سیصد",
          "چهارصد",
          "پانصد",
          "ششصد",
          "هفتصد",
          "هشتصد",
          "نهصد",
        ],
      ],
    };
  },
  components: {
    listofcomp,
  },
  methods: {
    changeNumber() {
      this.numberToLetter();
    },
    numberToLetter() {
      if (this.number == 1000000000000) this.resultN = "یک بیلیون";
      else if (this.number == "") this.resultN = "لطفا عدد را وارد کنید";
      else if (this.number.length == 1)
        this.resultN = this.length1(this.number);
      else if (this.number.length == 2)
        this.resultN = this.length2(this.number);
      else if (this.number.length == 3)
        this.resultN = this.length3(this.number);
      else if (this.number.length > 3 && this.number.length < 7)
        this.resultN = this.length4(this.number);
      else if (this.number.length > 6 && this.number.length < 10)
        this.resultN = this.length5(this.number);
      else if (this.number.length > 9 && this.number.length < 13)
        this.resultN = this.length6(this.number);
      else this.resultN = "این تبدیل تا 12 رقم را در بر میگیرد";
    },
    length1(L1) {
      return this.constLetters[0][L1];
    },
    length2(L2) {
      let temp = 0;
      if (L2 < 20) return this.constLetters[1][L2[1]];
      else {
        temp = this.constLetters[2][L2[0]];
        if (L2[1] != 0) {
          temp += " و " + this.length1(L2[1]);
        }
      }
      return temp;
    },
    length3(L3) {
      let temp = 0;
      temp = this.constLetters[3][L3[0]];
      if (L3.slice(-2) >= 10) temp += " و " + this.length2(L3.slice(-2));
      else {
        if (L3[2] != 0) temp += " و " + this.length1(L3.slice(-1));
      }
      return temp;
    },
    length4(x) {
      let L4 = "";
      if (x.length > 6) L4 = x.slice(x.length - 6, x.length);
      else L4 = x;
      let result = "";
      let temp = "";
      temp = L4.slice(0, L4.length - 3);

      if (temp.length == 1) result = this.length1(temp);

      if (temp.length == 2) result = this.length2(temp);

      if (temp.length == 3) result = this.length3(temp);

      if (x.length > 6 && L4.slice(0, L4.length - 3) == "000") result += " ";
      else result += " هزار ";

      temp = L4.slice(L4.length - 3, L4.length);

      if (temp != "000") {
        result += " و ";
        result += this.length3(temp);
      }
      return result;
    },
    length5(x) {
      let L5 = x;
      if (x.length > 9) this.length5 = x.slice(x.length - 9, x.length);
      else L5 = x;
      let result = "";
      let temp = "";
      temp = L5.slice(0, L5.length - 6);

      if (temp.length == 1) result = this.length1(temp);

      if (temp.length == 2) result = this.length2(temp);

      if (temp.length == 3) result = this.length3(temp);

      result += " میلیون ";

      temp = L5.slice(L5.length - 6, L5.length - 3);

      if (temp != "000") {
        result += " و ";
        result += this.length4(L5.slice(L5.length - 6, L5.length));
      } else if (L5.slice(L5.length - 3, L5.length) != "000")
        result += this.length3(L5.slice(L5.length - 3, L5.length));
      return result;
    },
    length6(L5) {
      let result = "";
      let temp = "";
      temp = L5.slice(0, L5.length - 9);

      if (temp.length == 1) result = this.length1(temp);

      if (temp.length == 2) result = this.length2(temp);

      if (temp.length == 3) result = this.length3(temp);

      result += " میلیارد ";

      temp = L5.slice(L5.length - 9, L5.length - 6);

      if (temp != "000") {
        result += " و ";
        result += this.length5(L5.slice(L5.length - 9, L5.length));
      } else if (L5.slice(L5.length - 6, L5.length - 3) != "000") {
        result += " و ";
        result += this.length4(L5.slice(L5.length - 6, L5.length));
      } else if (L5.slice(L5.length - 3, L5.length) != "000")
        result += this.length3(L5.slice(L5.length - 3, L5.length));
      return result;
    },
     callcomp(x){
        this.$emit('comp',x);
      }
  },
};
</script>

