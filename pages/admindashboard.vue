<template>
  <div class="block lg:flex">
    <div class="">
      <SidebarContainer>
        <template #hamburgermenuopen>
          <button class="">
            <img
              :src="require('@/assets/icons/openmenu.png')"
              class="w-10 mx-2 p-0"
            />
          </button>
        </template>

        <template #hamburgermenuclose>
          <button class="">
            <img
              :src="require('@/assets/icons/closemenu.png')"
              class="w-10 m-0 p-0"
            />
          </button>
        </template>

        <template #logo>
          <SidebarLogo />
        </template>

        <template #menu>
          <SidebarMenu path="./admindashboard">
            <div class="block lg:flex items-center gap-3">
              <div><SharedIcons icon_name="icon1"/></div>
              <div>Overview</div>
            </div>
          </SidebarMenu>

          <SidebarMenu path="./admindashboard">
            <div class="block lg:flex items-center gap-3">
              <div><SharedIcons icon_name="icon2"/></div>
              <div>Employee</div>
            </div>
          </SidebarMenu>

           <SidebarMenu path="./admindashboard">
            <div class="block lg:flex items-center gap-3">
              <div><SharedIcons icon_name="icon3"/></div>
              <div>Task</div>
            </div>
          </SidebarMenu>

          <SidebarMenu path="./admindashboard">
            <div class="block lg:flex items-center gap-3">
              <div><SharedIcons icon_name="icon4"/></div>
              <div>Management</div>
            </div>
          </SidebarMenu>
        </template>

        <template #logout>
          <div><SidebarLogout /></div>
        </template>
      </SidebarContainer>
    </div>
    <div class="w-full py-20 lg:py-0 lg:pl-60">
        <Header/>
        <div class="px-8 py-5 w-full text-center lg:text-left lg:py-10 lg:px-16">
          <div class="text-black text-2xl lg:text-4xl mb-2 font-bold">Overview</div>
          <div class="text-gray-400">Sunday,4 december 2022</div>
        </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>