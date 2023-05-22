<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulario para nova tarefa">
        <input type="text" class="input" placeholder="Descreva uma tarefa">
      </div>
      <div class="column">
        <Controles />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Controles from './Controles.vue'

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Formulario',
  components: { Controles }
})
</script>

<style scoped></style>