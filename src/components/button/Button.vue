<script setup lang="ts">
const props = defineProps(
    {
        displayValue: String,
        functionBtn: Function 
    }
)

const handleClick = (event: MouseEvent) => {
  if (props.functionBtn) {
    props.functionBtn(event);
  }
};


</script>

<template>
    <button class="bg-zinc-800 rounded-sm text-3xl" @click.prevent="handleClick">
        {{ props.displayValue }}
    </button>
</template>