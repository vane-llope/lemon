<template>
<div class="container">
   <hr class="mt-5 mb-5" />
    <div class="d-flex JS">
      <div>
        <listofcomp  @comp="callcomp" />
      </div>
  <div class="componentWidth">
    <h1 class="text-center">شمارش کاراکتر,کلمه و جمله</h1>
    <textarea
      class="form-control text-center"
      style="width:100%; height:260px"
      type=""
      placeholder="متن خود را وارد کنید"
      v-model="text"
    />
    <div>
      <div class="mt-3">
        <button
          class="btnM col-12 text-center text-light"
          type="button"
          @click="count"
        >
          تایید
        </button>
      </div>
    </div>

    <div class="mt-3 mb-5 text-center" style="height: 80px">
      <div class="card card-body" style="width: 100%">
        <p> تعداد کاراکتر: {{ char }}</p>
        <p> تعداد کلمه: {{ word }}</p>
        <p> تعداد جمله: {{ sentence }}</p>
      </div>
    </div>
  </div>
  </div>
</div>
</template>
<script>
import listofcomp from './listofcomp.vue'
export default {
  name: "typoStuff",
  data() {
    return {
      text: [],
      char: 0,
      word: 0,
      sentence: 0,
    };
  },
   components: {
    listofcomp,
  },
  methods: {
    count() {
        this.char=this.text.length
      if (this.text[this.text.length - 1] != ".") this.text += ".";
      this.word = 2;
      this.sentence = 0;
      let i;
      for (i = 0; i < this.text.length; i++) {
        if (this.text[i] == " ") this.word += 1;
        if (this.text[i] == ".") {
          this.sentence += 1;
        }
      }
      this.word+=this.sentence-2;
    },
      callcomp(x){
        this.$emit('comp',x);
      }
  },
};
</script>