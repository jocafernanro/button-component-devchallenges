<template>
  <div :class="`flex flex-row w-full md:w-${width} justify-between mb-6`">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    width: String,
  },
};
</script>

<style>
</style>