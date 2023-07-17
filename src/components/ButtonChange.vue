<template>
  <button class="btn btn-primary mt-2 me-3" @click="tombolubah">
    Change Text
  </button>
</template>

<script>
export default {
  methods: {
    tombolubah() {
      this.$emit("change");
    }
  }
};
</script>
