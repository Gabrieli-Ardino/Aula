<template>
  <input @input="adicionarBit" />
</template>

<script>
export default {
  props: ["value"],
  data() {
    return {
      entrada: this.value,
    };
  },
  watch: {
    entrada() {
      this.$emit("input", this.entrada);
    },
  },
  methods: {
    adicionarBit(e) {
      this.entrada = e.target.value;
    },
  },
};
</script>

<style>
</style>