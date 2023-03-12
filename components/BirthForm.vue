<template>
  <form>


    <div class="form-group">
      <input type="text" class="form-control" name="name" placeholder="Nome" v-model="signupForm.name">
    </div>
    <div class="form-group">
      <input type="email" class="form-control" name="email" placeholder="email@domínio.com.br"
             v-model="signupForm.email">
    </div>
    <div class="form-group">
      <input type="datetime-local" class="form-control" name="birthdate" v-model="signupForm.birthDate">
    </div>
    <div v-if="showCityFindInput" class="input-group mb-3">
      <input type="text" v-model.lazy="cityFindInput" class="form-control" name="city"
             placeholder="Cidade de Nascimento">
      <div class="input-group-append">
        <button type="button" :disabled="loading" @click="searchCity" class="input-group-text" id="basic-addon2">
          <font-awesome-icon v-if="!loading" :icon="['fas','search']"  />
          <font-awesome-icon v-else :icon="['fas','spinner']"  />
        </button>
      </div>
    </div>
    <ul v-if="showCityFindInput" class="list-group mb-3">
      <li v-for="(item,x) in cityList" @click="selectCity(item)" :key="x"
          class="list-group-item list-group-item-action">{{ item.label }}
      </li>
    </ul>
    <div v-else class="input-group mb-3">
      <input type="text" class="form-control" disabled v-model="selectedCity.label">
      <div class="input-group-append">
        <button @click="clearSelectedCity" class="input-group-text" id="basic-addon2">
          <font-awesome-icon :icon="['fas','trash']"  />
        </button>
      </div>
    </div>
    <button :disabled="loading" type="submit" class="btn btn-secondary-dark btn-lg btn-block p-3"
            @click.stop.prevent="submit()">
      <span class="h2">Fazer meu mapa astral!</span>
    </button>
  </form>
</template>

<script>
// const reTelefone = /([0-9+\-()\s]){8,15}/;
const reEmail = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
const reDatetime = /\d{4}-[01]\d-[0-3]\dT[0-2]\d:[0-5]\d/

export default {
  name: 'BirthForm',
  watch: {
    cityFindInput(newVal) {
      if (newVal.length > 2) {
        this.searchCity()
      }
    }
  },
  data: () => ({
    cityFindInput: "",
    selectedCity: {},
    signupForm: {
      name: "",
      email: "",
      city: "",
      birthDate: ""
    },
    cityList: [],
    loading: false
  }),
  computed: {
    showCityFindInput() {
      return this.selectedCity.value == null
    }
  },
  beforeDestroy() {
    this.cityFindInput = ""
    this.selectedCity = {}
    this.signupForm = {}
  },
  methods: {
    submit() {
      // Validação
      const validName = this.signupForm.name.length > 2
      const validEmail = reEmail.test(this.signupForm.email)
      const validBirthdate = reDatetime.test(this.signupForm.birthDate)
      const validCity = this.signupForm.city != ""

      console.log('Validação', validName, validEmail, validBirthdate, validCity)

      if( !validName || !validEmail || !validBirthdate || !validCity ){
        alert('Verifique os campos!')
        return
      }

      // Verificar Network
      if (this.loading) {
        return
      }
      this.loading = true
      this.$axios.post(`/api/site/contact?domain=andrezaastrologia.com.brs`, this.signupForm).then((res) => {
        this.$router.push('/checkout')
      }).catch(e => {
        console.log("ERRO ENVIAR CONTATO", e)
      }).finally(() => {
        this.loading = false
      });
    },
    selectCity(city) {
      this.signupForm.city = city.value
      this.selectedCity = city
    },
    async searchCity() {
      if (this.loading) {
        return
      }
      this.loading = true
      this.$axios.get(`/client/v1/location?city=${this.cityFindInput}`).then((res) => {
        this.cityList = res.data
      }).catch(e => {
        console.log("ERRO ENVIAR CONTATO", e)
      }).finally(() => {
        this.loading = false
      });
    },
    clearSelectedCity() {
      this.cityFindInput = ""
      this.selectedCity = {}
      this.cityList = []
    }
  }
}
</script>

<style scoped>

</style>
