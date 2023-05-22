<template>
  <section>
    <strong>{{ tempoFormatado }}</strong>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Cronometro",
  computed: {
    tempoFormatado(): string {
      return new Date(this.tempoSegundos * 1000).toISOString().substr(11, 8)
    }
  },
  props: {
    tempoSegundos: {
      type: Number,
      default: 0
    }
  }
});
</script>

<style lang="scss" scoped></style>