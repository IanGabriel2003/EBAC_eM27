<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'adicionar',
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case 'adicionar':
          return this.numero1 + this.numero2;
        case 'subtrair':
          return this.numero1 - this.numero2;
        case 'multiplicar':
          return this.numero1 * this.numero2;
        case 'dividir':
          return this.numero1 / this.numero2;
        default:
          return 0;
      }
    },
  },
};
</script>

<template>
  <input @keyup="evento => numero1 = (evento.target.value)" type="number" placeholder="Numero 1" name="" id="">
  <select id="operacao" v-model="operacao">
    <option value="adicionar">+</option>
    <option value="subtrair">-</option>
    <option value="multiplicar">*</option>
    <option value="dividir">/</option>
  </select>
  <input @keyup="evento => numero2 = (evento.target.value)" type="number" placeholder="Numero 2" name="" id="">
  Resultado: {{ resultado }}
</template>

<style scoped>
</style>