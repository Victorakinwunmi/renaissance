<template>
<div class="bg-gray-100 w-full h-screen flex items-center">
    <div class=" hidden lg:block w-7/12">
     <div class="bg-no-repeat bg-cover bg-center"  :style="{backgroundRepeat: 'no-repeat' + ';',backgroundImage:'url(' + require('@/assets/images/login_image.jpg') + ')',}">
       <div class="bg-black flex items-end bg-opacity-40 h-screen">
            <div class="text-white mx-16 max-w-sm text-2xl md:text-3xl lg:text-4xl font-mono mb-8 font-bold uppercase ">Staff management information system</div>
       </div>
     </div>
    </div>
    <div class="w-full px-4 lg:w-5/12 lg:p-0">
        <div v-show="login_type === true" class="w-full  shadow-2xl rounded-2xl md:p-0 lg:py-10 md:w-4/6 lg:w-5/6 xl:w-4/6 mx-auto">
            <img :src="require('@/assets/icons/profile.png')" class="w-16 mx-auto mb-2">
            <div class="bg-white px-4 py-10 md:px-8 lg:px-14">
                <div class="flex justify-center gap-6 w-full mb-6">
                    <button class="text-xl border-b-2 border-blue-400 p-2 uppercase text-black font-bold">Admin</button>
                    <button class="text-xl uppercase font-bold" @click="toggleFunction()">Staff</button>
                </div>
                <input type="text" Placeholder="Admin Id No" class="block mx-auto w-full border-blue-300 border rounded-lg mb-4 px-2 py-4 outline-none">
                <input type="email" Placeholder="Email" class="block mx-auto w-full border-blue-300 border rounded-lg mb-4 px-2 py-4 outline-none">
                <div class="flex items-center justify-between border-blue-300 border px-2 py-4 rounded-lg mb-4 ">
                <input :type="show_password?'text':'password'" Placeholder="Password" class="block w-full mx-auto outline-none">
                <PasswordIcons @togglePassword="showPassword" />
                </div>
                <div class="flex items-center gap-2 mb-6">
                    <input type="checkbox" class="cursor-pointer">
                    <div class="text-base font-semibold">Remember to keep me logged in</div>
                </div>
                <div class="w-full flex justify-center mt-8 ">
                 <button class="px-6 py-2 duration-500 ease-in-out hover:bg-blue-900 hover:border-blue-900 border border-blue-400 bg-blue-400 text-white font-bold text-black rounded-md">Login</button>
                </div>
            </div>
        </div>
        <div v-show="login_type === false" class="w-full shadow-2xl rounded-2xl md:p-0 lg:py-10 md:w-4/6 lg:w-5/6 xl:w-4/6 mx-auto">
            <img :src="require('@/assets/icons/profile.png')" class="w-16 mx-auto mb-2">
            <div class="bg-white px-4 py-10 md:px-8 lg:px-14">
                <div class="flex justify-center gap-6 w-full mb-6">
                    <button class="text-xl uppercase text-black font-bold"  @click="toggleFunctionii()">Admin</button>
                    <button class="text-xl border-b-2 border-blue-400 p-2 uppercase text-black font-bold">Staff</button>
                </div>
                <input type="email" Placeholder="Email" class="block mx-auto w-full border-blue-300 border rounded-lg mb-4 px-2 py-4 outline-none">
                <div class="flex items-center justify-between border-blue-300 border px-2 py-4 rounded-lg mb-4 ">
                <input :type="show_password?'text':'password'" Placeholder="Password" class="block w-full mx-auto outline-none">
                <PasswordIcons @togglePassword="showPassword" />
                </div>
                <div class="flex items-center gap-2 mb-6">
                    <input type="checkbox" class="cursor-pointer">
                    <div class="text-base font-semibold">Remember to keep me logged in</div>
                </div>
                <div class="w-full flex justify-center mt-8 ">
                 <button class="px-6 py-2 duration-500 ease-in-out hover:bg-blue-900 hover:border-blue-900 border border-blue-400 bg-blue-400 text-white font-bold text-black rounded-md">Login</button>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
 data(){
    return{
        show_password:false,
        login_type:true,
    }
 },
 methods:{
    showPassword(){
        this.show_password = !this.show_password
      },
    toggleFunction(){
        if(this.login_type == true){
          this.login_type=false
        }
        else{
          return
        }
    },
    toggleFunctionii(){
        if(this.login_type == false){
          this.login_type=true
        }
        else{
          return
        }
    },

 }
};
</script>
