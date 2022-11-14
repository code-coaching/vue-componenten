<template>
  <div>{{ title }}</div>

  <p>{{ hallo }}</p>
  <CustomButton :title="'Voeg o toe'" :callback="showLog" @geklikt="onClick()" />
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import CustomButton from 'components/CustomButton.vue';

export default defineComponent({
  components: {
    CustomButton,
  },
  setup() {
    const hallo = ref('hallo');

    const onClick = () => hallo.value += 'o';
    const showLog = () => console.log('haha vanuit Secondary');

    return {
      title: 'Secondary page',
      onClick,
      hallo,
      showLog
    };
  },
});
</script>
