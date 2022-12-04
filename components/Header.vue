<template>
  <div class="block lg:flex justify-between border-b-4 border-gray-200 w-full py-8 px-16">
     <div class="hidden lg:block border border-transparent w-2/4">
       <div class="w-4/12 gap-2 rounded-md p-2 lg:flex items-center bg-gray-100 ">
          <img :src="require('@/assets/icons/search.png')" class="w-4 h-4">
          <input type="search" placeholder="Search here..." class="w-full text-gray-500 outline-none cursor-pointer bg-transparent">
       </div>
     </div>
     <div>

     </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>