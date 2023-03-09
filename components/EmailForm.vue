<template>
  <form>
    <div class="form-group">
      <input type="email" class="form-control" name="email" >
    </div>
    <button type="submit" class="btn btn-primary btn-lg btn-block" @click.stop.prevent="submit()">
      Quero me conhecer melhor!
    </button>
  </form>
</template>

<script>
export default {
  name: 'EmailForm',
  methods: {
    submit () {
      this.$router.push('/checkout')
    }
  }
}
</script>

<style scoped>

</style>
