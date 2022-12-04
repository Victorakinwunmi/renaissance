<template>
  <div class="">
    <a href="/">
      <img :src="path ? path : require('@/assets/icons/logout.png')" class="mx-auto w-8" />
    </a>
   
  </div>
</template>


<script>
export default {
   props :{
     path:{
       type: String,
       default:''
     } 
   }
}
</script>

<style>

</style>