<template>
  <main>
    <section class="bg-light">
      <div class="container my-3">
        <div class="row">
          <div class="col-12 col-md-6">
            <div class="embed-responsive embed-responsive-16by9 my-md-5">
              <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/zpOULjyy-n8?rel=0" allowfullscreen />
            </div>
          </div>
          <div class="col-12 col-sm-12 col-md-6">
            <div class="p-5">
              <h1>Lorem ipsum dolor sit amet.</h1>
              <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla dictum sapien nisl, eu euismod lectus dictum a. Ut laoreet nibh et nulla molestie, sit amet finibus tellus consectetur.</p>
              <email-form />
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="container-fluid bg-secondary-light py-5">
      <div class="text-center mb-5">
        <h2 class="text-white">Lorem ipsum dolor sit amet.</h2>
        <p class="w-md-50 text-white m-auto">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla dictum sapien nisl, eu euismod lectus dictum a. Ut laoreet nibh et nulla molestie, sit amet finibus tellus consectetur.
        </p>
      </div>

      <div class="card-deck">

        <div v-for="i in 3" class="card border-light">
          <img src="https://images.unsplash.com/photo-1511945863317-d60e146e9016?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTM0fHx3b21hbnxlbnwwfDB8MHx8&auto=format&fit=crop&w=800&q=60" class="card-img-top" alt="Imagem 1">
          <div class="card-body">
            <h5 class="card-title">
              Card title
            </h5>
            <p class="card-text">
              This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.
            </p>
            <p class="card-text">
              <small class="text-muted">Last updated 3 mins ago</small>
            </p>
          </div>
        </div>

      </div>
    </section>

    <section class="container-fluid bg-light">
      <div class="row">
        <div class="d-none d-md-table-cell col-md-6 bg-1" />
        <div class="col-md-6 p-5">
          <h1 class="mt-5 mb-3">
            Only the finest,<br>locally sourced produce.
          </h1>
          <p>All fresh ingredients in our dishes are sourced from local farms and farmer's markets. Making use of only fresh, seasonally available produce infuses the dishes we prepare with a unique authenticity.</p>
          <email-form />
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
