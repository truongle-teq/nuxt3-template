<script setup lang="ts">
interface ButtonProps {
  text: string;
  type?: "primary" | "secondary" | "tertiary";
}

type EmitsType = {
  (event: "onClickEmit", value: string): void;
};

const props = withDefaults(defineProps<ButtonProps>(), {
  type: "primary",
});

const emit = defineEmits<EmitsType>();

const hello = "hello";
console.log(hello);

const handleClick = () => {
  emit("onClickEmit", "I am clicked");
};

onBeforeMount(() => {
  console.log("before mount");
});

onMounted(() => {
  console.log("mounted");
});
</script>

<template>
  <button :class="['btn', props.type]" @click="handleClick">
    {{ props.text }}
  </button>
</template>
