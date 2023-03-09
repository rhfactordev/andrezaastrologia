<template>
  <main>

    <section>
      <div class="container py-5">
        <h1 class="text-center mb-5">Checkout de Pagamento</h1>
        <div class="row">
          <div class="col-md-4 mb-4 pr-3">
            <h4 class="d-flex justify-content-between align-items-center mb-3">
              <span class="text-muted">Seu carrinho</span>
              <span class="badge badge-secondary badge-pill">1</span>
            </h4>
            <ul class="list-group mb-3">
              <li class="list-group-item d-flex justify-content-between lh-condensed">
                <div>
                  <h6 class="my-0">Mapa Astral</h6>
                  <small class="text-muted">Mapa astralogólico em PDF.</small>
                </div>
                <span class="text-muted">R$47,90</span>
              </li>
              <li class="list-group-item d-flex justify-content-between">
                <span>Total (R$)</span>
                <strong>R$47,90</strong>
              </li>
            </ul>
          </div>
          <div class="col-md-8 mb-4 pl-3">
            <h2 class="h3 mb-3">Escolha a forma de pagamento</h2>
            <b-tabs content-class="mt-3">
              <b-tab title="Pix" active>

                <div class="text-center">

                  <a class="btn btn-secondary text-white btn-lg p-3 my-3"><span class="h4">Finalizar compra com Pix</span></a>

                </div>

              </b-tab>
              <b-tab title="Cartão de Crédito">

                <form id="form-checkout">
                  <div id="form-checkout__cardNumber" class="container"></div>
                  <div id="form-checkout__expirationDate" class="container"></div>
                  <div id="form-checkout__securityCode" class="container"></div>
                  <input type="text" id="form-checkout__cardholderName" />
                  <select id="form-checkout__issuer"></select>
                  <select id="form-checkout__installments"></select>
                  <select id="form-checkout__identificationType"></select>
                  <input type="text" id="form-checkout__identificationNumber" />
                  <input type="email" id="form-checkout__cardholderEmail" />


                  <button type="submit" id="form-checkout__submit" class="btn btn-secondary text-white btn-lg p-3 my-3"><span class="h4">Finalizar com Cartão de Crédito</span></button>

                  <progress value="0" class="progress-bar">Carregando...</progress>
                </form>


              </b-tab>
            </b-tabs>
          </div>
        </div>
      </div>
    </section>




  </main>
</template>

<script>

export default {
  name: 'CheckoutPage',
  head () {
    return {
      title: 'Checkout de Pagamento',
      script: [
        // { src: 'https://sdk.mercadopago.com/js/v2', pbody: true, async : false },
        // { src: 'mercadopago.js', body: true },
      ],
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
#form-checkout {
  display: flex;
  flex-direction: column;
  max-width: 600px;
}
</style>
