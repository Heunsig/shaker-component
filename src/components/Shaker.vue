<script setup>
// TODO: 프로토타입. 리팩토링 및 최적화 필요
import { useSlots, h } from 'vue';

const props = defineProps({
  modelValue: {
    type: Boolean,
    default: false
  }
});
const emits = defineEmits(['update:modelValue']);
const slots = useSlots();

function startShaking() {
  setTimeout(() => {
    emits('update:modelValue', false);
  }, 500);
}

function render() {
  if (!slots.default) return;

  if (props.modelValue) {
    startShaking();
  }

  return slots.default().map(element => {
		return h(element, { 
			class: props.modelValue ? 'shaker shaker--shaking' : undefined 
		})
	});
}
</script>

<template>
  <render/>
</template>

<style scoped>
:global(.shaker.shaker--shaking){
  animation: horizontal-shaking 0.25s infinite;
}

@keyframes horizontal-shaking {
  0% { transform: translateX(0) }
  25% { transform: translateX(5px) }
  50% { transform: translateX(-5px) }
  75% { transform: translateX(5px) }
  100% { transform: translateX(0) }
}
</style>