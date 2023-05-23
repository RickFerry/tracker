<template>
  <div class="box formulario">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulario para nova tarefa">
        <input type="text" class="input" placeholder="Descreva uma tarefa" v-model="descricao">
      </div>
      <div class="column">
        <Controles @stoppar="finalizarTarefa" />
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
  emits: ['aoSalvar'],
  data() {
    return {
      descricao: ''
    }
  },
  methods: {
    finalizarTarefa(tempo: number): void {
      this.$emit('aoSalvar', {
        tempoSegundos: tempo,
        descricao: this.descricao
      })
      this.descricao = ''
    }
  },
  components: { Controles }
})
</script>

<style>
.formulario {
  color: var(--texto-primario);
  background-color: var(--bg-primario);
}
</style>