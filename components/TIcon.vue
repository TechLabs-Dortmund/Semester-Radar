<template>
  <svg class="icon" :class="{ 'icon-spin': spin }">
    <use :xlink:href="`#${icon}`" />
    <!-- Only show the title if the variable has been passed in props -->
    <title v-if="title">{{ title }}</title>
  </svg>
</template>

<script>
export default {
  name: 'TIcon',
  props: {
    icon: {
      type: String,
      required: true,
    },
    spin: {
      type: Boolean,
    },
    title: {
      type: String,
      default: '',
    },
  },
}
</script>

<style>
svg.icon {
  fill: currentColor;
  height: 1em;
  margin-bottom: 0.125em;
  vertical-align: middle;
  width: 1em;
}

svg.icon-spin {
  animation: icon-spin 2s infinite linear;
}

@keyframes icon-spin {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(359deg);
  }
}
</style>
