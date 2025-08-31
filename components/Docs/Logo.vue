<template>
  <section class=" space-y-2">

    <header class="space-y-2">
      <h4 class=" font-semibold text-blue-600 uppercase tracking-wide mb-2">Basic Element</h4>
      <h1 class="font-semibold text-gray-900">Logo Utama</h1>
      <p class="text-gray-600 text-lg">
        Logo adalah representasi utama identitas
        <strong>Clipan Finance</strong>.
        Penggunaan logo yang benar menjaga konsistensi dan kredibilitas brand di semua media.
      </p>
    </header>

    <UiSeparator />

    <section class="space-y-2">
      <h2 class="text-lg font-semibold text-gray-900">Versi Logo</h2>
      <ul class="list-disc pl-6 text-gray-700">
        <li><strong>Logo Utama</strong> → digunakan di sebagian besar media.</li>
        <li><strong>Logo Horizontal</strong> → digunakan pada media dengan ruang terbatas.</li>
        <li><strong>Logo Monogram</strong> → untuk ruang kecil seperti favicon, icon aplikasi.</li>
      </ul>
    </section>

    <section class="space-y-3 ">
      <h2 class="text-lg font-semibold text-gray-900">Clear Space</h2>
      <p class="text-gray-700">
        Pastikan ada area kosong di sekeliling logo minimal
        <strong>1x tinggi huruf “C”</strong> dari Clipan.
      </p>

      <div>
        <div class="justify-center bg-white p-2 border border-slate-200 hover:shadow-lg shadow-primary rounded-lg">
          <div class=" grids border border-slate-100 grid w-full h-full min-h-40 place-items-center p-4 rounded">
            <img src="/hero.png" alt="Logo Clear Space" class="max-w-xs border rounded" />
          </div>
          <div class="flex pt-2 items-center justify-between">
            <h4 class="font-semibold uppercase ">Logo Utama</h4>
            <p class="text-sm opacity-80">Display (3rem / 48px)
            </p>
          </div>
        </div>
        <div
          class="relative rounded-lg overflow-hidden hover:shadow-lg shadow-primary h-full max-h-24 bg-slate-200 border border-slate-300 ">
          <button type="button"
            class=" absolute right-2 top-2 shadow-md px- flex justify-center items-center size-11 text-sm font-medium rounded-lg border border-transparent bg-white text-primary hover:bg-blue-600 focus:outline-hidden focus:bg-blue-700 disabled:opacity-50 disabled:pointer-events-none">
            <Icon name="lucide:clipboard" class="size-4" />
          </button>
          <pre class="">
          <code>
            {{ '<img src="/hero.png" alt="Logo Clear Space" class="max-w-xs border rounded" />' }}
          </code>
        </pre>
        </div>
      </div>


      <Alert type="info" icon="lucide:info" title="Tip">
        Jangan menempatkan logo terlalu dekat dengan teks atau elemen grafis lain.
      </Alert>
    </section>

    <section class="space-y-2">
      <h2 class="text-lg font-semibold text-gray-900">Minimum Size</h2>
      <ul class="list-disc pl-6 text-gray-700">
        <li>Cetak: <strong>20 mm</strong></li>
        <li>Digital: <strong>100 px</strong></li>
      </ul>
    </section>

    <section class="space-y-2">
      <h2 class="text-lg font-semibold text-gray-900">Larangan</h2>
      <ul class="list-disc pl-6 text-gray-700">
        <li>Jangan mengubah warna logo.</li>
        <li>Jangan menambahkan efek (shadow, gradient).</li>
        <li>Jangan memutar atau mengubah proporsi logo.</li>
      </ul>
    </section>
  </section>
</template>

<script setup lang="ts">
// This component is auto-registered by Nuxt (components/ dirs).
</script>

<style scoped>
.grids {
  background-color: #f7fbff;
  background-image:
    linear-gradient(to right, rgba(37,
        99,
        235,
        0.05) 1px, transparent 1px),
    linear-gradient(to bottom, rgba(37, 99, 235, 0.05) 1px, transparent 1px);
  background-size: 40px 40px;
}
</style>
