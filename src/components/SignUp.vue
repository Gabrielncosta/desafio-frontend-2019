<template>
<div class="height">
  <div class="container">
    <form>
      <div class="form-row">
        <div class="form-group col-md-6">
          <label for="inputName">Nome*</label>
          <input type="email" class="form-control" id="inputEmail4" >
        </div>
        <div class="form-group col-md-6">
          <label for="inputZip">CEP*</label>
          <input v-model="cep" @keyup="postCep" type="text" class="form-control" id="inputZip">
        </div>
      </div>
      <div class="form-row">
        <div class="form-group col-md-6">
          <label for="inputEmail4">E-mail*</label>
          <input type="email" class="form-control" id="inputEmail4">
        </div>
        <div class="form-group col-md-4">
          <label for="inputAddress">Endereço*</label>
          <input type="text" v-model="rua" class="form-control" id="inputAddress">
        </div>
        <div class="form-group col-md-2">
          <label for="inputAddress">Número*</label>
          <input type="text" class="form-control" id="inputAddress">
        </div>
      </div>
      
      <div class="form-row">
        <div class="form-group col-md-6">
          <label for="inputEmail4">CPF</label>
          <input type="email" class="form-control" id="inputEmail4">
        </div>
        <div class="form-group col-md-3">
          <label for="inputAddress">Complemento</label>
          <input type="text" v-model="complemento" class="form-control" id="inputAddress">
        </div>
        <div class="form-group col-md-3">
          <label for="inputAddress">Bairro*</label>
          <input type="text" v-model="bairro" class="form-control" id="inputAddress">
        </div>
      </div>
      <div class="form-row">
        <div class="form-group col-md-3">
          <label for="inputEmail4">Data de Nascimento*</label>
          <input type="email" class="form-control" id="inputEmail4" placeholder="dd/mm/yyyy">
        </div>
        <div class="form-group col-md-3">
          <label for="inputEmail4">Telefone*</label>
          <input type="email" class="form-control" id="inputEmail4" >
        </div>
        <div class="form-group col-md-4">
          <label for="inputCity">Cidade</label>
          <input type="text" v-model="cidade" class="form-control" id="inputCity">
        </div>
        <div class="form-group col-md-2">
          <label for="inputState">Estado</label>
          <input type="text" v-model="estado" id="inputState" class="form-control">
        </div>
      </div>
      <div class="d-flex justify-content-end">
        <button type="submit" class="btn btn-buy">Concluir compra</button>
      </div>
    </form>
  </div>
</div>
</template>

<script>
  const axios = require('axios');
  export default{
      name: 'Header',
      data() {
        return {
          cep: "",
          address: {},
          bairro: '',
          rua: '',
          complemento: '',
          cidade: '',
          estado: '',

        }
      },
      methods: {
        postCep() {
          axios.get(`https://viacep.com.br/ws/${this.cep}/json/`).then(response => {
            let address = response.data;
            this.bairro = address.bairro;
            this.rua = address.logradouro;
            this.complemento = address.complemento;
            this.cidade = address.localidade;
            this.estado = address.uf;
          })
          .catch(error => {
          })
        }
    
      },
  }
</script>


<style lang="scss" scoped>
.form-group {
  text-align: start !important;
}

.height {
  height: 70vh;
}

.btn-buy {
  background-color: #8e36b7;
  font-family: 'SourceSansPro-Regular';
  width: 300px;
  color: #fff;
}

@media (max-width: 770px) {
  .height {
    height: auto;
  }

  .btn-buy {
    margin-right: auto;
    margin-left: auto;
  }
}

</style>
