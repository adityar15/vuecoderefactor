<template>
  <form class="flex flex-col mt-10 space-y-7" @submit.prevent="submitForm">
    <FormGroup
      v-if="formType == 'signup'"
      v-model="user.fullname"
      label="Full Name"
      placeholder="Enter full name"
      type="text"
      :error="errors.fullname"
    />
    <FormGroup
      v-model="user.email"
      label="Email"
      placeholder="Enter email"
      type="email"
      :error="errors.email"
    />
    <FormGroup
      v-model="user.password"
      label="Password"
      placeholder="Enter password"
      type="password"
      :error="errors.password"
    />

    <div class="text-center">
      <button class="button">
        {{ formType == "signup" ? "Sign Up" : "Sign In" }}
      </button>
    </div>
  </form>
</template>

<script setup>
import { reactive } from "vue";
import { defineAsyncComponent } from "vue";

const FormGroup = defineAsyncComponent(() =>
  import("@/components/Form/FormGroup.vue")
);


defineProps({
    formType: {
        type: String,
        default: "signup"
    }
})

const emit = defineEmits(["submit"]);

function submitForm() {
  if(user.fullname == "")
  {
    errors.fullname = "Name is required"
    return
  }
  emit("submit", user);
}

const user = reactive({
  fullname: "",
  email: "",
  password: "",
});

const errors = reactive({
  fullname: "",
  email: "",
  password: "",
});


</script>

<style scoped>
.button {
  @apply bg-purple-500 text-gray-50 px-9 py-2 rounded;
}
</style>
