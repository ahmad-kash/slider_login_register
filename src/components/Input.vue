<template>
  <input
    :id="props.id"
    :name="props.name"
    :type="props.type"
    :autocomplete="props.autocomplete"
    :required="props.required"
    v-model="value"
    :placeholder="props.placeholder"
    class="border-b border-bottom-gray-300 focus:outline-none sm:min-w-[300px] px-1 py-1"
  />
</template>
<script setup>
import { computed } from "vue";

const props = defineProps({
  modelValue: String,
  id: String,
  name: String,
  type: String,
  required: {
    type: Boolean,
    required: false,
    default: false,
  },
  placeholder: String,
  autocomplete: String,
});
const emit = defineEmits(["update:modelValue"]);

const value = computed({
  get() {
    return props.modelValue;
  },
  set(value) {
    emit("update:modelValue", value);
  },
});
</script>
