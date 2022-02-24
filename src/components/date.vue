<template>
<div class="container">
<hr class="mt-5 mb-5" />
    <div class="d-flex JS">
      <div>
         <listofcomp  @comp="callcomp" />
      </div>
    <div class="componentWidth">
     <div >
       <p id="clock"> </p>
       <p id="date"></p>
        <p id="dateL"></p>
     </div>
    





    </div>
    </div>
</div>
    
</template>
<script>
import listofcomp from './listofcomp.vue';
export default {
    name:'date',
    components: {
    listofcomp,
  },
  methods: {
       callcomp(x){
        this.$emit('comp',x);
      },
     
  },
  mounted() {
    var month= ["January","February","March","April","May","June","July",
            "August","September","October","November","December"];

    var days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];        


    let myClock = () =>{
      let myDate = new Date();
      //clock
          let clock=document.querySelector("#clock")
          clock.textContent = myDate.getHours() +' : ' +myDate.getMinutes() +' : ' + myDate.getSeconds()
      //date
       let date=document.querySelector("#date")
        date.textContent = myDate.getFullYear() + ' / '+ (myDate.getMonth()+1) + ' / '+ myDate.getDate() 
       //date to letter
        let dateL=document.querySelector("#dateL")
        dateL.textContent = days[myDate.getDay()] + ' ' + myDate.getDate() +' '+ month[myDate.getMonth()] + ' ' + myDate.getFullYear()
     
        }
        myClock();
        setInterval(myClock,1000);

  },
 
}
</script>