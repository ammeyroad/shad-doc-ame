<script setup>
import { ref, watch } from 'vue'

defineProps({
  content: {
    type: String,
    required: true,
  },
  label: {
    type: String,
    required: true,
  },
  VariantShow: {
    type: String,
    default: '',  // atau 'visible' misalnya, sesuai kebutuhan
  },
  variants: {
    type: Array,
    default: () => [],
  },
  codeSnippet: {
    type: String,
    required: true,
  }
})

const showCode = ref(false)
const copied = ref(false)

function copyToClipboard() {
  navigator.clipboard.writeText(props.codeSnippet)
  copied.value = true
  setTimeout(() => (copied.value = false), 2000)
}
</script>

<template>
  <div class="bg-white p-2 rounded-xl hover:shadow-soft border border-gray-100 duration-200">
    <div v-show="!showCode"
      class="h-48 bg-slate-50 border-slate-200 rounded-lg overflow-hidden mx-auto flex items-center justify-center">
      <div class="w-full text-center " v-html="content"></div>
    </div>

    <div v-show="showCode"
      class="h-48 bg-slate-100 overflow-hidden rounded-lg shadow-[inset_0px_0px_14px_2px_rgba(26,_26,_26,_0.2)] relative  content-center">
      <div :class="VariantShow" class="text-xs h-8 absolute top-0 m-2 bg-white p-1.5 rounded">
        <select class="outline-none">
          <option disabled>variant</option>
          <option v-for="v in variants" :key="v" :value="v">{{ v }}</option>
        </select>
      </div>
      <pre class="text-xs text-wrap p-2 overflow-hidden"><code>{{ codeSnippet }}</code></pre>
    </div>

    <div class="flex justify-between items-center mt-2">
      <p>{{ label }}</p>
      <div class="bg-slate-100 p-1 flex gap-1 items-center rounded-lg relative">
        <div class="w-8 h-8 p-1.5 rounded cursor-pointer relative flex items-center justify-center" :class="{
          'bg-transparent': showCode || copied,
          'bg-white': !showCode && !copied
        }" @click="copyToClipboard" title="Copy code to clipboard">
          <Icon v-if="!copied" name="solar:clipboard-add-line-duotone" class="size-5" />
          <Icon v-else name="solar:check-circle-bold-duotone" class="size-5 text-secondary" stroke-width="3"
            stroke="currentColor" />
        </div>

        <div class="w-8 h-8 p-1.5 rounded cursor-pointer relative flex items-center justify-center" :class="{
          'bg-white': showCode,
          'bg-transparent': !showCode
        }" @click="showCode = !showCode" title="Toggle code snippet">
          <Icon v-if="showCode" name="solar:eye-bold-duotone" class="size-5" />
          <Icon v-else name="solar:eye-closed-bold-duotone" class="size-5" />
        </div>
      </div>
    </div>
  </div>
</template>