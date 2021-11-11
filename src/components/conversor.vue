<template>
  <div class="principal">
    <div class="entradaDados">
      <label for="entradaBinario">Valor Binário</label>
      <InputBin v-model="entrada" name="entradaBinario" />
    </div>
    <button @click="converter" class="btConversor">Converter</button>
    <div class="saidaDados">
      <label for="saidaDecimal">Valor Decimal</label>
      <input v-model="saida" disabled name="saidaDecimal" />
    </div>
  </div>
</template>

<script>
import InputBin from "@/components/InputBin";
export default {
  components: { InputBin },
  data() {
    return {
      entrada: "",
      saida: "",
    };
  },
  methods: {
    bin2dec(valor) {
      const valorInvertido = valor.split("").reverse();
      let total = 0,
        pos = 0;
      for (const bit of valorInvertido) {
        total += bit * 2 ** pos;
        pos++;
      }
      return total;
    },
    converter() {
      this.saida = this.bin2dec(this.entrada);
    },
  },
};
</script>

<style>
</style>