<template>
  <div>
     <div @click="togglePassword" :class="is_hidden ? 'hidden':'block'">
        <img
            :src="require('@/assets/icons/invisible.png')"
            class="w-6 h-5 mr-4 cursor-pointer"
        />
    </div>
    
    <div @click="togglePassword" :class="is_hidden ? 'block':'hidden'">
        <img
            :src="require('@/assets/icons/visible.png')"
            class="w-6 h-5 mr-4 cursor-pointer"
        />
    </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            is_hidden: true,
        }
    },
    methods:{
      togglePassword(){
        this.is_hidden = !this.is_hidden
        this.$emit("togglePassword")
      }
    }
};
</script>

<style>
</style>