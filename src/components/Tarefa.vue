<template>
  <Box>
    <div class="columns">
      <div class="column is-7">{{ tarefa.descricao || 'Tarefa sem descrição' }}</div>
      <div class="column">
        <Cronometro :tempoSegundos="tarefa.tempoSegundos" />
      </div>
    </div>
  </Box>
</template>

<script lang="ts">
import { PropType, defineComponent } from 'vue';
import Cronometro from './Cronometro.vue';
import ITarefa from '@/interfaces/ITarefa';
import Box from './Box.vue';

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Tarefa",
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true
    }
  },
  components: { Cronometro, Box }
})
</script>

<style scoped></style>