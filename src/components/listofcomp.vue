<template>

    <div class="container" >
      
        <!--table-->
        <div class="tableM">
          <table class="table-bordered table table-striped table-hover">
            <thead>
              <tr class="text-center tableBg text-light">
                <th>ابزار ها</th>
              </tr>
            </thead>
            <tbody class="text-center">
              <tr @click="component='passwordGenerator'; callcomp();" >
                <td>تولید بسورد تصادفی</td>
              </tr>
              <tr  @click="component='melicode'; callcomp();">
                <td>صحت کد ملی</td>
              </tr>
              <tr  @click="component='engToPer'; callcomp();">
                <td>تبدیل عدد فارسی و انکلیسی</td>
              </tr>
              <tr @click="component='numToLetter'; callcomp();" >
                <td>تبدیل عدد به حروف</td>
              </tr>
              <!--<tr  @click="component='birth'; callcomp();">
                <td>محاسبه ی سن</td>
              </tr>-->
              <tr  @click="component='date'; callcomp();">
                <td> تاریخ امروز</td>
              </tr>
              <tr @click="component='percentage'; callcomp();">
                <td> ...افزایش درصد حقوق، قیمت و </td>
              </tr>
              <tr   @click="component='MBI'; callcomp();">
                <td>شاخص توده ی بدنی</td>
              </tr>
              <tr  @click="component='typoStuff'; callcomp();">
                <td>شمارش کاراکتر,کلمه و جمله</td>
              </tr>
            </tbody>
          </table>
        </div>
    </div>

</template>

<script>
export default {
    name:'listofcomp',
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
}
</script>