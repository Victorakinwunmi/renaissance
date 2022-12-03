<template>
<div class="bg-gray-100 w-full h-screen flex items-center">
    <div class=" hidden lg:block w-7/12">
     <div class="bg-no-repeat bg-cover bg-center"  :style="{backgroundRepeat: 'no-repeat' + ';',backgroundImage:'url(' + require('@/assets/images/login_image.jpg') + ')',}">
       <div class="bg-black flex items-end bg-opacity-40 h-screen">
            <div class="text-white mx-16 max-w-sm text-2xl md:text-3xl lg:text-4xl font-mono mb-8 font-bold uppercase ">Staff management information system</div>
       </div>
     </div>
    </div>
    <div class="w-full lg:w-5/12 lg:p-0">
        <div :class="wrong_password? 'block':'hidden'">
            <div class="bg-red-500 p-2 w-full mb-4 flex items-center justify-between text-center">
              <h1 class="text-white text-sm w-full">User password is incorrect</h1>
              <img :src="require('@/assets/icons/close.png')" class="w-6 cursor-pointer" @click="closeWrongPass()">
            </div>
        </div>
        <div :class="not_exist? 'block':'hidden'">
            <div class="bg-red-500 p-2 w-full mb-4 flex items-center justify-between text-center">
              <h1 class="text-white text-sm w-full">User does not exist</h1>
              <img :src="require('@/assets/icons/close.png')" class="w-6 cursor-pointer" @click="closeNotExist()">
            </div>
        </div>
        <form @submit.prevent="adminAunthetication" v-show="login_type === true" class="w-full p-4 shadow-2xl rounded-2xl lg:px-0 lg:py-10 md:w-4/6 lg:w-5/6 xl:w-4/6 mx-auto">
            <img :src="require('@/assets/icons/profile.png')" class="w-16 mx-auto mb-2">
            <div class="bg-white px-4 py-10 md:px-8 lg:px-14">
                <div class="flex justify-center gap-6 w-full mb-6">
                    <button class="text-xl border-b-2 border-blue-400 p-2 uppercase text-black font-bold">Admin</button>
                    <button class="text-xl uppercase font-bold" @click="toggleFunction()">Staff</button>
                </div>
                <input type="text" v-model="admin_id" Placeholder="Id No" class="block mx-auto w-full border-blue-300 border rounded-lg mb-4 px-2 py-4 outline-none">
                <input type="email" v-model="admin_email" Placeholder="Email" class="block mx-auto w-full border-blue-300 border rounded-lg mb-4 px-2 py-4 outline-none">
                <div class="flex items-center justify-between border-blue-300 border px-2 py-4 rounded-lg mb-4">
                <input v-model="admin_password" :type="show_password?'text':'password'" Placeholder="Password" class="block w-full mx-auto outline-none">
                <PasswordIcons @togglePassword="showPassword" />
                </div>
                <div class="flex items-center gap-2 mb-6">
                    <input type="checkbox" class="cursor-pointer">
                    <div class="text-base font-semibold">Remember to keep me logged in</div>
                </div>
                <div class="w-full flex justify-center mt-8 ">
                  <LoadingButton :loadingText="'Auntheticating..'" :loading="loading_state">
                    <template #login>LOGIN</template>
                  </LoadingButton>
                </div>
            </div>
        </form>
        <div v-show="login_type === false" class="w-full shadow-2xl rounded-2xl p-4 lg:px-0 lg:py-10 md:w-4/6 lg:w-5/6 xl:w-4/6 mx-auto">
            <img :src="require('@/assets/icons/staff.png')" class="w-16 mx-auto mb-2">
            <div class="bg-white px-4 py-10 md:px-8 lg:px-14">
                <div class="flex justify-center gap-6 w-full mb-6">
                    <button class="text-xl uppercase text-black font-bold"  @click="toggleFunctionii()">Admin</button>
                    <button class="text-xl border-b-2 border-blue-400 p-2 uppercase text-black font-bold">Staff</button>
                </div>
                <input type="email" v-model="staff_email" Placeholder="Email" class="block mx-auto w-full border-blue-300 border rounded-lg mb-4 px-2 py-4 outline-none">
                <div class="flex items-center justify-between border-blue-300 border px-2 py-4 rounded-lg mb-4 ">
                <input v-model="staff_password" :type="show_password?'text':'password'" Placeholder="Password" class="block w-full mx-auto outline-none">
                <PasswordIcons @togglePassword="showPassword" />
                </div>
                <div class="flex items-center gap-2 mb-6">
                    <input type="checkbox" class="cursor-pointer">
                    <div class="text-base font-semibold">Remember to keep me logged in</div>
                </div>
                <div class="w-full flex justify-center mt-8 ">
                  <LoadingButton :loadingText="'Auntheticating..'" :loading="loading_state">
                    <template #login>LOGIN</template>
                  </LoadingButton>
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
        admin_id:"",
        admin_email:"",
        admin_password:"",
        staff_email:"",
        staff_password:"",
        loading_state: false,
        wrong_password:false,
        not_exist:false,
    }
 },
 methods:{
    adminAunthetication(){
      this.Load()
      setTimeout(this.adminValidation,3000)
    },
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
    adminValidation() {
        clearTimeout(this.dLoad())
        let adminAccount = {
            id_no: "0001",
            email: "adexvictor94@gmail.com",
            password: "victor",
        };
        
        if(this.admin_email =="" || this.admin_password =="" || this.admin_id == ""){
            return
        }else{
            
        }

        if (this.admin_email == adminAccount.email && this.admin_id == adminAccount.id_no){
                if (adminAccount.password == this.admin_password) {
                   window.location.replace('admindashboard')
                } else {
                  this.wrong_password=!this.wrong_password
                }
            }else {
               this.not_exist=!this.not_exist
            }
    
    },
    Load(){
        if(this.admin_email =="" && this.admin_password ==""){
        return
        }else{
        this.loading_state=!this.loading_state
        }
    },

    dLoad(){
        this.loading_state=false
    },
    closeWrongPass(){
        this.wrong_password=!this.wrong_password
    },
    closeNotExist(){
        this.not_exist=!this.not_exist
    },

 }
};
</script>
