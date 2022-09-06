<template>
    <div class="inputSearch">
        <div class="input-group mb-3">
            <input type="text" class="form-control" placeholder="Pesquisa uma cidade" aria-label="Recipient's username" aria-describedby="button-addon2">
            <button class="btn btn-outline-secondary" type="button" id="button-addon2">Pesquisar</button>
        </div>
    </div>
  </template>
  
  <script>
    import 'bootstrap/dist/css/bootstrap.css'
    export default {
      name:'InputSearch',
      data() {
        return {
          text: ''
        }
      }
    }
  </script>

  <style scoped>
    
  </style>