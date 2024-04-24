<script>
export default {
  name: 'BaseButton',
}
</script>

<template>
  <button @click="$listeners">
    <slot>Mettre un nom au slot !!</slot>
  </button>
</template>

<style></style>