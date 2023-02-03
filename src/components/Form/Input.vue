<template>
      <input
        v-bind="$attrs"
        class="input"
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
      />
</template>

<script setup>
defineProps({
    modelValue: String | Number
})
const emit = defineEmits(["update:modelValue"])
</script>

<style scoped>
.input {
  @apply border border-gray-200 p-2 rounded-md w-full;
}

</style>