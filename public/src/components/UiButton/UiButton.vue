<template>
  <button :class="$style.button" :data-layout="props.layout" :disabled="props.isDisabled" :type="props.type">
    <slot></slot>
  </button>
</template>

<script setup lang="ts">
interface IProps {
  layout?: 'primary' | 'secondary';
  type?: 'submit' | 'button';
  isDisabled?: boolean;
}

const props = withDefaults(defineProps<IProps>(), {
  layout: 'primary',
  type: 'button',
});
</script>

<style module lang="scss">
.button {
  position: relative;
  display: inline-flex;
  gap: 8px;
  align-items: center;
  justify-content: center;
  height: 40px;
  padding: 16px 32px;
  font-size: 1.1rem;
  line-height: 1.5;
  color: #ff8c00;
  background: #8a2be2;
  border: 2px solid #32cd32;
  border-radius: 16px;

  &:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
  }
}

&[data-layout='secondary'] {
  color: #ff8c00;
  background-color: transparent;
  border-color: #32cd32;
}
</style>
