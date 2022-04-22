<template>
  <svg :class="propClass" xmlns="http://www.w3.org/2000/svg" version="1.1">
    <path :d="path" :stroke="stroke" />
  </svg>
</template>

<script>
export default {
  props: {
    path: {
      type: String,
      default: ''
    },
    stroke: {
      type: String,
      default: 'black'
    },
    propClass: {
      type: String,
      default: 'h-6 w-6'
    }
  }
}
</script>
