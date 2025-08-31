<script setup lang="ts">
import { ref } from 'vue'

const props = defineProps({
  code: { type: String, required: true },
  language: { type: String, default: 'html' },
})

const copied = ref(false)

async function copyToClipboard() {
  try {
    await navigator.clipboard.writeText(props.code)
    copied.value = true
    setTimeout(() => (copied.value = false), 1500)
  } catch (e) {
    // no-op
  }
}
</script>

<template>
  <div class="relative rounded-lg overflow-hidden bg-slate-200 border border-slate-300">
    <button
      type="button"
      class="absolute right-2 top-2 shadow-md flex justify-center items-center size-9 rounded-md border border-transparent bg-white text-primary hover:bg-blue-600 hover:text-white focus:outline-hidden focus:bg-blue-700 disabled:opacity-50 disabled:pointer-events-none"
      :aria-label="copied ? 'Copied' : 'Copy code'"
      :title="copied ? 'Copied' : 'Copy code'"
      @click="copyToClipboard"
    >
      <Icon v-if="!copied" name="lucide:clipboard" class="size-4" />
      <Icon v-else name="lucide:check" class="size-4" />
    </button>

    <pre class="text-xs  text-wrap p-2 w-full">
      <code :class="`language-${language}`">{{ code }}</code>
    </pre>
  </div>
  
</template>

