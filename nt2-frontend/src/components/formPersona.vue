<template>
  <div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        id="input-group-1"
        label-for="input-1"
      >
        <b-form-input
          id="input-1"
          v-model="form.dni"
          required
          placeholder="DNI"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2"  
      label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.apellido"
          required
          placeholder="Apellido"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2"  
      label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.nombre"
          required
          placeholder="Nombre"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2"  
      label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.fechaNac"
          required
          placeholder="Fecha de nacimiento"
        ></b-form-input>
        
      </b-form-group>


        
      <b-form-group id="input-group-3" label-for="input-3">
        <b-form-select
          id="input-3"
          v-model="form.genero"
          :options="géneros"
          required
        ></b-form-select>
      </b-form-group>


      <b-button type="submit" variant="primary">Guardar</b-button>

    </b-form>
    
  </div>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          dni: '',
          apellido: '',
          nombre: '',
          fechaNac: '',
          checked: []
        },
        géneros: [{ text: 'Seleccione uno', value: null }, 'Masculino', 'Femenino', 'Otros'],
        show: true
      }
    },
    methods: {
      onSubmit(evt) {
        evt.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(evt) {
        evt.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.form.food = null
        this.form.checked = []
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>
   
