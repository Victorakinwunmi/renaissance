<template>
  <div class="mb-10">
    <a href="/">
      <img :src="path ? path : require('@/assets/icons/logout.png')" class="mx-auto" />
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