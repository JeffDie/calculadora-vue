<script setup>
  import { reactive } from 'vue';

  const estado = reactive ({
    numero1: '',
    numero2: '',
    filtro: 'somar',
    resultado: ''
  })

  const calcularResultado = () => {
    switch(estado.filtro){
      case 'somar':
        return estado.resultado = estado.numero1 + estado.numero2;
      case 'subtrair':
        return estado.resultado = estado.numero1 - estado.numero2;
      case 'dividir':
        return estado.resultado = estado.numero1 * estado.numero2;
      case 'multiplicar':
        return estado.resultado = estado.numero1 / estado.numero2;
      default:
        filtro.resultado = 0;
    }
  }
</script>

<template>
  <div class="container">
    <header class="d-flex p-5 mb-4 mt-4 bg-secondary justify-content-center bg-gradient text-white">
      <h1>Calculadora</h1>
    </header>
    <form>
      <div class="row">
        <div class="col-md-4">
          <input v-model="estado.numero1" @input="calcularResultado" type='number' placeholder="Digite o primeiro valor:" class="form-control" required>
        </div>
        <div class="col-md-4">
          <select v-model="estado.filtro" class="form-control" @change="calcularResultado">
            <option value="somar">Somar</option>
            <option value="subtrair">Subtrair</option>
            <option value="dividir">Dividir</option>
            <option value="multiplicar">Multiplicar</option>
          </select>
        </div>
        <div class="col-md-4">
          <input v-model="estado.numero2"  @input="calcularResultado" type='number' placeholder="Digite o segundo valor:" class="form-control" required>
        </div>
        <div class="mt-4 d-flex justify-content-center bg-secondary p-3 fs-4 bg-gradient text-white">
          <strong>Resultado: {{ estado.resultado }}</strong>
        </div>
      </div>
    </form>
  </div>
</template>

<style scoped>

</style>
