<template>
  <div>
    <h1>MEJORES DELANTEROS DEL FUTBOL INTERNACIONAL</h1>
    <!-- inicio tabla de delanteros-->
    <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-center">
            NOMBRE
          </th>
          <th class="text-center">
            APELLIDO
          </th>
          <th class="text-center">
            EDAD
          </th>
          <th class="text-center">
            EMAIL
          </th>
          <th class="text-center">
            ACCIONES
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="item in personajes"
          :key="item.name"
        >
          <td>{{ item.nombre }}</td>
          <td>{{ item.apellido }}</td>
          <td>{{ item.edad }}</td>
          <td>{{ item.email }}</td>
          <td>
            <v-btn
              color="accent"
              levation="12"
              rounded
              x-small
            >ELIMINAR</v-btn>
          </td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
  <!-- fin tabla de jugadores --> 
  </div>
</template>

<script>
import store from "../store/index.js";
export default {
    data: () => {
        return {};
    },
    methods: {},
    created: () => {
        //accede a las acciones del store
        store.dispatch("getPersonajes");
    },
    computed: {
        personajes: () => {
            return store.state.personajes;
        }
    }
};
</script>

<style>
</style>