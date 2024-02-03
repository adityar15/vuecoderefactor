<template>
    <div class="form-group">
        <Label :class="labelClasses">{{label}}</Label>
        <Input v-model="model" :class="inputClasses" :placeholder="placeholder" :type="type" />
        <span v-if="error" class="text-red-500 text-sm">{{error}}</span>
    </div>
</template>

<script setup>
import {defineAsyncComponent} from 'vue'

const Input = defineAsyncComponent(() => import('./Input.vue'))
const Label = defineAsyncComponent(() => import('./Label.vue'))

// const emit = defineEmits(["update:modelValue"])

const model = defineModel()

defineProps({
    type: String,
    placeholder: String,
    label: String,
    labelClasses: String,
    inputClasses: String,
    // modelValue: String | Number,
    error: String
})


function passInputValue(value){
    emit("update:modelValue", value)
}

</script>

<style scoped>
.form-group {
  @apply flex flex-col space-y-4;
}
</style>