<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

<input v-model="message" placeholder="edit me">
<p>Message is: {{ message }}</p>

   <div>
     
   
   <div>
   <b-card
    no-body
    style="max-width: 15rem;"
    img-src="https://placekitten.com/380/200"
    img-alt="Image"
    img-top
    >
    <h4 slot="header">CUIL</h4>

    <b-list-group flush>
      <b-list-group-item>Apellido, Nombre</b-list-group-item>
    </b-list-group>

    <b-card-body>
      <b-button variant="success" >Autorizar</b-button>
    <b-button variant="danger" >Denegar</b-button>

    </b-card-body>

  </b-card>
</div>
</div>

  </div>







</template>

<script>
  export default {
    name: 'HelloWorld',
    props: {
      msg: String
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h3 {
    margin: 40px 0 0;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>