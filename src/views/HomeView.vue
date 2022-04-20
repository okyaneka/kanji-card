<script setup lang="ts">
import TheWelcome from "@/components/TheWelcome.vue";
import { computed } from "@vue/reactivity";
import { reactive, ref } from "vue";

const counter = reactive({
  count: 1,
});
const label = ref(null);

const textCounter = computed(() => {
  return `${label.value || ""}: ${counter.count}`;
});

function handleOnInput(event) {
  label.value = event.target.value;
}
</script>

<template>
  <main>
    <TheWelcome :label="textCounter" @change:text="handleOnInput" />
  </main>
</template>
