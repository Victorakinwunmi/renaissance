<template>
  <div class="block lg:flex">
    <div class="">
      <SidebarContainer>
        <template #hamburgermenuopen>
          <button class="">
            <img
              :src="require('@/assets/icons/profile.png')"
              class="w-8 m-0 p-0"
            />
          </button>
        </template>

        <template #hamburgermenuclose>
          <button class="">
            <img
              :src="require('@/assets/icons/profile.png')"
              class="w-8 m-0 p-0"
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
    <div class="w-full"></div>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>