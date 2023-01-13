<script setup>
const { defaultTransition, twitterBorderColor } = useTailwindConfig()
const wrapperClasses = computed(
  () => `${defaultTransition} ${twitterBorderColor}`
)
</script>

<template>
  <div
    class="p-3 border-b hover:bg-gray-100 dark:hover:bg-dim-300 cursor-pointer"
    :class="wrapperClasses"
  >
    <slot />
  </div>
</template>
