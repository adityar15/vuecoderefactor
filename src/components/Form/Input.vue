<template>
      <input
        v-bind="$attrs"
        class="input"
        v-model="model"
      />
</template>

<script setup>
// defineProps({
//     modelValue: String | Number
// })
// const emit = defineEmits(["update:modelValue"])
const model = defineModel()
</script>

<style scoped>
.input {
  @apply border border-gray-200 p-2 rounded-md w-full;
}

</style>