<template>
  <main>

    <section class="bg-light">
      <div class="container my-3">
        <div class="row">
          <div class="col-12 col-md-6 offset-md-3 text-center">
            <h1>Obrigado!</h1>
            <p>Cras elit dui, mollis in pellentesque vitae, tristique eget lacus. Mauris non porta lectus, et tristique est. Vivamus ut quam ac arcu vulputate vehicula quis nec nisl. Etiam cursus eu nunc a dignissim. Nam scelerisque tristique nunc, id ultricies neque euismod nec. </p>

            <a class="btn btn-secondary text-white btn-lg">Clique aqui para fazer o Download da Previsão para Câncer</a>

          </div>
        </div>
      </div>
    </section>

    <section class="bg-secondary">
      <div class="container">
        <div class="row">
          <div class="col-12 col-md-6 py-3">
            <div class="embed-responsive embed-responsive-16by9 my-md-5">
              <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/zpOULjyy-n8?rel=0" allowfullscreen />
            </div>
          </div>
          <div class="col-12 col-md-6 py-3">
            <h2 class="text-white h1 my-5">Cras elit dui, mollis in pellentesque vitae, tristique eget lacus!</h2>
            <p class="h5 mb-4">Cras elit dui, mollis in pellentesque vitae, tristique eget lacus. Mauris non porta lectus, et tristique est. Vivamus ut quam ac arcu vulputate vehicula quis nec nisl. Etiam cursus eu nunc a dignissim. Nam scelerisque tristique nunc, id ultricies neque euismod nec. </p>

            <p class="h1 mb-3 text-dark p-3 text-center"><mark> De  <del>R$150,00</del> por R$47,90 </mark></p>

            <birth-form />

          </div>
          </div>
      </div>
    </section>




  </main>
</template>

<script>

export default {
  name: 'IndexPage',
  head () {
    return {
      title: 'Mapa Aastral - Conhecimento em suas mãos',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'FDescrição da página'
        }

      ]
    }
  }
}
</script>

<style scoped>
.bg-1{
  background-image: url('https://images.unsplash.com/photo-1664575601786-b00156752b61?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NXx8d29tYW58ZW58MHwxfDB8fA%3D%3D&auto=format&fit=crop&w=800&q=60');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 600px!important;
}
</style>
