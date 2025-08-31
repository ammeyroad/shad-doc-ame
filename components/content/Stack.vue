<template>
  <UiCard class=" overflow-hidden border-0 bg-white rounded-xl hover:shadow-lg [&:not(:first-child)]:mt-5">
    <div v-for="(slot, i) in $slots.default?.() ?? []" :key="i" class="bg-purple-100">
      <component :is="slot" :in-stack="true" class="rounded-b" />
    </div>
  </UiCard>

</template>

<script setup lang="ts">
defineSlots();
</script>