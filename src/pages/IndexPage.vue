<template>
  <div>{{ title }}</div>

  <p>{{ counter }}</p>
  <CustomButton :title="'Klik hier'" :callback="showAlert" @geklikt="onClick()" />
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import CustomButton from 'components/CustomButton.vue';

export default defineComponent({
  components: {
    CustomButton,
  },
  setup() {
    const counter = ref(0);

    const onClick = () => counter.value++;
    const showAlert = () => alert('hihi vanuit IndexPage');

    return {
      title: 'Index page',
      counter,
      onClick,
      showAlert
    };
  },
});
</script>
