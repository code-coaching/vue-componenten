<template>
  <button @click="onClick()">
    {{ title }}
  </button>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    title: {
      type: String,
      required: true,
    },
    callback: {
      type: Function,
      required: true,
    },
  },
  emits: ['geklikt'],
  setup(props, context) {
    const onClick = () => {
      props.callback();
      context.emit('geklikt')
    }
    
    return {
      onClick
    };
  },
});
</script>

<style lang="scss" scoped>
button {
  cursor: pointer;
  background-color: #000;
  color: #fff;
  border: 1px solid deeppink;
}
</style>
