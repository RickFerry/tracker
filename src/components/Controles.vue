<template>
  <div class="is-flex is-align-items-center is-justify-content-space-between">
    <Cronometro :tempoSegundos="tempoSegundos" />
    <button class="button" @click="iniciar" :disabled="play">
      <span class="icon">
        <i class="fas fa-play"></i>
      </span>
      <span>play</span>
    </button>
    <button class="button" @click="finalizar" :disabled="!play">
      <span class="icon">
        <i class="fas fa-stop"></i>
      </span>
      <span>stop</span>
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Cronometro from './Cronometro.vue';

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Controles",
  data() {
    return {
      tempoSegundos: 0,
      cronometro: 0,
      play: false
    };
  },
  methods: {
    iniciar() {
      this.play = true;
      this.cronometro = setInterval(() => {
        this.tempoSegundos++;
      }, 1000);
    },
    finalizar() {
      this.play = false;
      clearInterval(this.cronometro);
    }
  },
  components: { Cronometro }
})
</script>

<style lang="scss" scoped></style>