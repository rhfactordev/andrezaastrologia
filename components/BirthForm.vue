<template>
  <form>

    <div class="form-group">
      <input type="text" class="form-control" name="name" placeholder="Nome" >
    </div>
    <div class="form-group">
      <input type="email" class="form-control" name="email" placeholder="email@domínio.com.br" >
    </div>
    <div class="form-group">
      <input type="datetime-local" class="form-control" name="birthdate">
    </div>
    <div class="form-group">
      <input type="text" class="form-control" name="city" placeholder="Cidade de Nascimento" >
    </div>


    <button type="submit" class="btn btn-secondary-dark btn-lg btn-block p-3" @click.stop.prevent="submit()">
      <span class="h2">Fazer meu mapa astral!</span>
    </button>
  </form>
</template>

<script>
export default {
  name: 'BirthForm',
  methods: {
    submit () {
      this.$router.push('/checkout')
    }
  }
}
</script>

<style scoped>

</style>
