<template>
  <v-container>
      <encabezado />
      <v-row>
        <v-col>
          <h1 class="text-center">Calculadora Básica</h1>
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <v-text-field
            label="Número 1"
            :rules="rules"
            hide-details="auto"
            v-model="n1"
          ></v-text-field>
        </v-col>
        <v-col>
          <v-text-field
          label="Número 2"
          :rules="rules"
          hide-details="auto"
          v-model="n2"
          ></v-text-field>
        </v-col>
      </v-row>
      <br />
      <v-row>
        <v-col class="text-right">
          <v-btn
            color="primary"
            elevation="2"
            outlined
            rounded
            small
            @click="suma()"
            >suma</v-btn>
        </v-col>
        <v-col class="text-center">
          <v-btn
            color="primary"
            elevation="2"
            outlined
            rounded
            small
            @click="resta()"
            >resta</v-btn>
        </v-col>
        <v-col class="text-center">
          <v-btn
            color="primary"
            elevation="2"
            outlined
            rounded
            small
            @click="multiplica()"
            >multiplica</v-btn>
        </v-col>
        <v-col class="text-left">
            <v-btn
            color="primary"
            elevation="2"
            outlined
            rounded
            small
            @click="divide()"
            >divide</v-btn>
        </v-col>
      </v-row>
      <br />
      <span>{{ respuesta }}</span>
  </v-container>
</template>

<script>
import Encabezado from './Encabezado.vue';
export default {
  name: 'CalculadoraBasica',
  components: {
      Encabezado
  },
    data:()=>{
        return {
            n1: null,
            n2: null,
            respuesta: "",
            rules: [
              value => !!value || 'Requerido',
              value => (value && value.length >= 1) || 'Min 1 caracteres',
      ],
        }
    },
    methods:{
        suma(){
            this.respuesta = parseInt(this.n1) + parseInt(this.n2);
        },
        resta(){
            this.respuesta = parseInt(this.n1) - parseInt(this.n2);
        },
        multiplica(){
            this.respuesta = parseInt(this.n1) * parseInt(this.n2);
        },
        divide(){
            if (parseInt(this.n2)!=0) {
                this.respuesta = parseInt(this.n1) / parseInt(this.n2);}
            else {
                this.respuesta = "NO SE PUEDE DIVIDIR ENTRE CERO";
            }
        },
    },
}
</script>

<style>

</style>