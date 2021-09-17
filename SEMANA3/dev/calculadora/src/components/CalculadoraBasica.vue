<template>
  <div>
      <h1>Calculadora Básica</h1>
      <v-text-field
       label="Número 1"
       :rules="rules"
       hide-details="auto"
       v-model="n1"
      ></v-text-field>
      <v-text-field
       label="Número 2"
       :rules="rules"
       hide-details="auto"
       v-model="n2"
      ></v-text-field>
      <br />
      <v-btn
        color="primary"
        elevation="2"
        outlined
        rounded
        small
        @click="suma()"
        >suma</v-btn>
      <v-btn
        color="primary"
        elevation="2"
        outlined
        rounded
        small
        @click="resta()"
        >resta</v-btn>
      <v-btn
        color="primary"
        elevation="2"
        outlined
        rounded
        small
        @click="multiplica()"
        >multiplica</v-btn>
        <v-btn
        color="primary"
        elevation="2"
        outlined
        rounded
        small
        @click="divide()"
        >divide</v-btn>
      <br />
      <span>{{ respuesta }}</span>
  </div>
</template>

<script>
export default {
      name: 'CalculadoraBasica',
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