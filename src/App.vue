<template> 

  <div>
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-F3w7mX95PdgyTmZZMECAngseQB83DfGTowi0iMjiWaeVhAn4FJkqJByhZMI3AhiU" crossorigin="anonymous">
    <AppNav></AppNav>
      <div class="container">
            <header>
                <h1>Almacén central de productos - ACME SL</h1>
            </header>
      </div>  
    <ProductsTable></ProductsTable>
    <section>
      <NewForm></NewForm>
    </section>    
</div>
  
</template>

<script>
import AppNav from './components/AppNav.vue'
import ProductsTable from './components/ProductsTable.vue'
import NewForm from './components/NewForm.vue'
import "bootstrap/dist/css/bootstrap.min.css"
import "bootstrap"

export default {
  name: 'App',
  components: {
    AppNav,
    ProductsTable,
    NewForm
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
