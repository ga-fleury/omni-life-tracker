<template>
  <header
    class="
      w-full
      max-w-full
      bg-gray-700
      flex
      justify-between
      h-16
      content-center
      px-4
      py-1
    "
  >
    <span class="text-5xl text-gray-50 m-0">OmniTracker</span>
    <div class="w-1/3 flex content-center justify-end py-2.5">
      <button class="text-gray-50 border-gray-50 border-2 px-8 rounded-md">
        login
      </button>
      <button class="text-gray-50">why login?</button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderMain',
}
</script>

<style>
    button:not(:last-child) {
    margin-right: 16px;
    }
</style>