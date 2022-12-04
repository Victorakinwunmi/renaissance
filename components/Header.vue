<template>
  <div class="block lg:flex justify-between border-b-4 border-gray-200 w-full px-6 py-8 lg:px-16">
     <div class="hidden lg:block border border-transparent w-2/4">
       <div class="w-4/12 gap-2 rounded-md p-2 lg:flex items-center bg-gray-100 ">
          <img :src="require('@/assets/icons/search.png')" class="w-4 h-4">
          <input type="search" placeholder="Search here..." class="w-full text-gray-500 outline-none cursor-pointer bg-transparent">
       </div>
     </div>
     <div class="w-full lg:w-2/4 flex items-center gap-4 lg:gap-6 justify-center">
       <img :src="require('@/assets/icons/notification.png')" class="w-16 h-8 border-r-2 cursor-pointer px-4 border-gray-200">
       <div class="flex items-center gap-4">
        <button class="block h-8 w-8 rounded-full overflow-hidden border border-gray-100 mx-auto">
          <img :src="require('@/assets/images/dp.jpg')" class=" mx-auto object-cover" />
        </button> 
        <div class="">
            <div class="text-black font-bold">Victor Adedapo</div>
            <div class="font-bold text-gray-400">Admin</div>
        </div>
       </div>
     </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>