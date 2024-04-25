<script>
export default {
  name: 'BaseButton',
  methods: {
    handleClick() {
      this.$emit('click');
    }
  }
}
</script>

<template>
  <button @click="handleClick">
    <slot>Mettre un nom au slot !!</slot>
  </button>
</template>

<style></style>