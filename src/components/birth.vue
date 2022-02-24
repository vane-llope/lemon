<template>
<div class="container">
<hr class="mt-5 mb-5" />
    <div class="d-flex JS">
      <div>
         <listofcomp  @comp="callcomp" />
      </div>
    <div class="componentWidth">
    






    </div>
    </div>
</div>
    
</template>
<script>
import listofcomp from './listofcomp.vue';
export default {
    name:'birth',
    components: {
    listofcomp,
  },
  methods: {
       callcomp(x){
        this.$emit('comp',x);
      }
  },
}
</script>