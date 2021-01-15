<template>
  <label>
    <input
      type="text"
      :value="input"
      :placeholder="placeholder"
      @input="processData"
    />
  </label>
</template>

<script setup="emit">
import { ref,defineProps } from "vue";

defineProps({
  placeholder: { type: String, default: "Type something Here" },
  filter: { type: String, default: "name" },
});

const input = ref("")

const processData = (e) => {
  input.value= e.target.value
  console.log(emit);
  // $emit("filterEvent",{type:filter,value:input})

};
</script>
