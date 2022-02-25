<template>
  <div class="container">
    <hr class="mt-5 mb-5" />
    <div class="d-flex JS">
      <div>
         <listofcomp  @comp="callcomp" />
      </div>
      <div class="componentWidth">
          <h1 class="text-center">MBI محاسبه ی</h1>
        <input
          class="form-control text-center darkothercopm"
          type="text"
          placeholder="وزن خود را به واحد کیلو گرم وارد کنید به طور مثال 70"
          v-model="Weight"
        />
        <input
          class="form-control text-center mt-3 darkothercopm"
          type="text"
          placeholder="قد خود را (به واحد متر) وارد کنید به طور مثال 1.80"
          v-model="Height"
        />

        <div>
          <div class="mt-5">
            <button
              class="btnM col-12 text-center text-light"
              type="button"
              @click="calculate"
            >
              تایید
            </button>
          </div>
        </div>

        <div class="mt-3 text-center " style="min-height: 120px">
          <div class="card card-body darkothercopm" style="width: 100%">
            <p>{{ result }}</p>
          </div>
        </div>

      </div>
    </div>
    <div class="col-12 mt-5">
    
      
        <div class="text-center" style="min-height: 120px">
          <div class="card card-body text-end darkothercopm">
            <p>
              طبق گفته سازمان سلامت جهانی شاخص توده بدنی مناسب برای
              بزرگسالان بین ۱۸.۵ تا ۲۴.۵ تعیین شده است
            </p>
            افرادی که 25 تا 29 هستند دارای اضافه وزن بوده
            <p>وافرادی که بالاتر از ۳۰ باشند، جزء افراد چاق به حساب می آیند</p>
            افرادی که 40 به بالا هستند، از چاقی مفرط رنج می برند
            <p>
              شاخص توده بدنی خانمها و آقایان به همین صورت محاسبه شده و هیچ
              تفاوتی با یکدیگر ندارند
            </p>
            <p>
              حدود ۱.۵ میلیون از جمعیت بزرگسالان بالای ۲۰ سال (حدود ۳۴ درصد از
              جمعیت بزرگسالان جهان) از چاقی و اضافه وزن رنج می برند. انتظار می
              رود که این جمعیت تا سال ۲۰۳۰ به ۳ میلیون نفر برسد
            </p>
          </div>
        </div>
    </div>
  </div>
</template>
<script>
import listofcomp from './listofcomp.vue';
export default {
  name: "MBI",
  data() {
    return {
      Weight: "",
      Height: "",
      result: "",
    };
  },
  components: {
    listofcomp,
  },
  methods: {
    calculate() {
      this.result = this.Weight / (this.Height * this.Height);
    },
      callcomp(x){
        this.$emit('comp',x);
      }
  },
};
</script>