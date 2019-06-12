<template>
  <v-container fill-height fluid grid-list-xl>
    <v-layout justify-center wrap>
      <v-flex md12>
        <material-card :active-class="color" title="Personas" text="Listado Personas">
          <v-data-table :headers="headers" :items="items" hide-actions>

            <template slot="headerCell" slot-scope="{ header }">
              <span class="subheading font-weight-light text-success text--darken-3" v-text="header.text" />
            </template>

            
            <template slot="items" slot-scope="{ item }">
              <td>{{ item.dni }}</td>
              <td>{{ item.apellido }}</td>
              <td>{{ item.nombre }}</td>
              <td>{{ item.fechaNac }}</td>
              <td>{{ item.genero }}</td>
              <td>
                <v-checkbox :label="`${item.activa.toString()}`" v-model="checkbox" color="green"></v-checkbox>
              </td>
              <td>
                <v-btn color="success" @click="editarEmpresa(item)" small round>
                  <v-icon>mdi-pencil</v-icon>
                </v-btn>
                <v-btn color="danger" @click="eliminarEmpresa(item)" small round>
                  <v-icon>mdi-delete</v-icon>
                </v-btn>
                <v-tooltip top content-class="top">
                  <v-btn slot="activator" class="v-btn--simple" color="danger" icon>
                    <v-icon color="error">mdi-delete</v-icon>
                  </v-btn>
                  <span>Eliminar</span>
                </v-tooltip>
              </td>
            </template>

          </v-data-table>
        </material-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  import axios from "axios";
  export default {
    data: () => ({
      headers: [{
          sortable: false,
          text: 'DNI',
          value: 'dni'
        },
        {
          sortable: true,
          text: 'Apellido',
          value: 'apellido'
        },
        {
          sortable: false,
          text: 'Nombre',
          value: 'nombre'
        },
        {
          sortable: false,
          text: 'Fecha de nacimiento',
          value: 'fechaNac'
        },
        {
          sortable: false,
          text: 'Género',
          value: 'genero'
        }
      ],
      items: []
    }),
    methods: {
      editarPersona: function (item) {
        alert(`DNI A EDITAR ${item.cuit}`)
      },
      eliminarEa: function (item) {
        alert(`DNI A BORRAR ${item.cuit}`)
      }
    },
    mounted() {
      axios({
        method: "GET",
        "url": "http://localhost:8000/api/personas"
      }).then(result => {
        this.items = result.data;
      }, error => {
        console.error(error);
      });
    }
  }
</script>