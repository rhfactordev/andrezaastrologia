<template>
  <form>
    <div class="form-group">
      <input type="email" class="form-control" name="email" placeholder="email@domínio.com.br" >
    </div>
    <div class="form-group">
      <select class="form-control" name="sign" >
        <option value="aries">Áries</option>
        <option value="touro">Touro</option>
        <option value="gemeos">Gêmeos</option>
        <option value="cancer">Câncer</option>
        <option value="leao">Leão</option>
        <option value="virgem">Virgem</option>
        <option value="libra">Libra</option>
        <option value="escorpiao">Escorpião</option>
        <option value="sagitario">Sagitário</option>
        <option value="capricornio">Capricórnio</option>
        <option value="aquario">Aquário</option>
        <option value="peixes">Peixes</option>
      </select>
    </div>

    <button type="submit" class="btn btn-primary btn-lg btn-block py-3" @click.stop.prevent="submit()">
      <span class="h4">Quero minha previsão mensal!</span>
    </button>
  </form>
</template>

<script>
export default {
  name: 'EmailForm',
  methods: {
    submit () {
      this.$router.push('/obrigado')
    }
  }
}
</script>

<style scoped>

</style>
