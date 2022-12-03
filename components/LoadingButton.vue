<template>
  <div>
    <button
      :class="
        color ? color : 'hover:bg-blue-900 text-white'
      "
      @click="toggleLoad"
      :disabled="loading || disabled"
      class="
        font-bold
        rounded-md
        outline-none
        py-2
        px-8
        bg-blue-400
        duration-500
        ease-in-out
      "
    >
      <div class="flex items-center justify-center uppercase">
        <div v-if="loading" class="flex items-center">
          {{ loadingText }}
        </div>
        <div v-if="!loading">
          <slot name="login" />
        </div>
      </div>
    </button>
  </div>
</template>

<script>
export default {
  name: "LoadingButton",
  props: {
    loading: Boolean,
    color: String,
    disabled: Boolean,
    loadingText: String,
  },
  data() {
    return {
      loading_state: false,
    };
  },

  methods: {
    toggleLoad() {
      this.$emit("toggleLoad");
    },
  },
};
</script>
