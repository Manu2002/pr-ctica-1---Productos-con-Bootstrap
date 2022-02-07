<template>
     <div class="hidable row">
            <div class="col-sm-12 col-md-12 col-lg-12" id="almacen">
                <table class="table table-striped table-hover">
                    <thead class="thead-dark bg-light">
                        <tr>
                            <th>Id</th>
                            <th>Nombre</th>
                            <th>Uds.</th>
                            <th>Precio/u</th>
                            <th>Importe</th>
                            <th>Acciones</th>
                        </tr>
                    </thead>
                    <tbody>
                        <product-row v-for="product in productos" :key="product.id" :product="product"> </product-row>
                        <!-- Aquí insertaremos los productos-->
                    </tbody>
                    <tfoot>
                        <th colspan="4">Importe total del almacén:</th>
                        <th id="total">0.00 €</th>
                        <th></th>
                    </tfoot>
                </table>
            </div>
        </div>
</template>

<script>

import API from '../services/API'
import ProductRow from './ProductRow.vue'

export default {
  components: { ProductRow },  
    data(){
        return{
            productos:[],
        }
    }, 
    methods:{
        getData(){
          API.products.getAll()
        .then(response => this.productos=response.data)
        .catch(response => {
            if (!response.status) {// Si el servidor no responde 'response' no es un objeto sino texto
            alert('Error: el servidor no responde');
            console.log(response);
            } else {
            alert('Error '+response.status+': '+response.message);          
            }
            this.products=[];
        })
        }
    },
    mounted(){
        this.getData();
    },
}
</script>