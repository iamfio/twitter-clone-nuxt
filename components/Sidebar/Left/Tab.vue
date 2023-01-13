<script setup>
const { defaultTransition } = useTailwindConfig()

const { active } = defineProps({
  active: {
    type: Boolean,
    default: false,
  },
})

const textClasses = computed(() => (active ? 'font-semibold' : 'font-normal'))
</script>

<template>
  <NuxtLink
    to="#"
    class="flex items-center p-3 w-min text-dark hover:bg-gray-200 dark:hover:bg-dim-200 dark:text-white rounded-full"
    :class="defaultTransition"
  >
    <div class="w-6 h-6 text-dark" :class="defaultTransition">
      <slot name="icon" />
    </div>

    <div class="hidden ml-4 text-xl xl:block" :class="textClasses">
      <slot name="name" />
    </div>
  </NuxtLink>
</template>
