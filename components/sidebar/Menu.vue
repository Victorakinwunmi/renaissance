<template>
    <div class="my-6 text-black py-2 pl-2 pr-6 rounded-md text-center duration-500 ease-in-out hover:text-blue-600 font-bold hover:bg-gray-200">
        <a :href="path"><slot /></a>
    </div>
  
</template>

<script>
export default {
    props: {
        path: String,
    }

}
</script>

<style>

</style>