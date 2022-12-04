<template>
  <div class="">
    <div
      :class="is_revealed ? 'hidden' : 'block lg:hidden'"
      @click="showMenu"
      class="p-4 fixed"
    >
      <div class="">
        <slot name="hamburgermenuopen"></slot>
      </div>
    </div>

    <div
      :class="is_revealed ? 'block' : 'hidden'"
      @click="hideMenu"
      class="p-4 float-right"
    >
      <div>
        <slot name="hamburgermenuclose"></slot>
      </div>
    </div>

    <div :class="is_revealed ? 'block ' : 'hidden' " class="h-screen lg:block border-r-2 border-gray-200 bg-gray-100 text-center fixed">
      <div class="h-full flex flex-col justify-between lg:gap-16 px-10 bg-gray-100">
        <div>
          <slot name="logo" />
        </div>

        <div class="">
          <slot name="menu" />
        </div>

        <div class="text-black text-center mb-10 lg:mt-72">
          <slot name="logout" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      is_revealed: false,
    };
  },
  methods: {
    showMenu() {
      this.is_revealed = true;
    },
    hideMenu() {
      this.is_revealed = false;
    },
  },
};
</script>

<style>
</style>