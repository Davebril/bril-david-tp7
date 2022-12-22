<template >

  <section>

    <div class="jumbotron">
      <h2>Usuarios Registrados</h2>
      <hr />
      <br />
    </div>  

    <table class="table">
      <thead>
        <tr>
          <th scope="col">Nombre</th>
          <th scope="col">Edad</th>
          <th scope="col">Email</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="(usuario, index) in usuarios" :key="index">
          <td>{{ usuario.nombre }}</td>
          <td>{{ usuario.edad }}</td>
          <td>{{ usuario.email }}</td>
        </tr>
      </tbody>
    </table>

  </section>
 

</template>

<script >

  export default  {
    name: 'src-componentes-usuarios',
    props: [],
    mounted () {
      this.getPostAxios()
    },
    data () {
      return {
        url: 'https://63680e7cedc85dbc84e13567.mockapi.io/tp7',
        usuarios: []

      }
    },
    methods: {
      async getPostAxios() {
        try {
          let response = await this.axios(this.url)
          let respuesta = response.data
          console.log(respuesta)
          this.usuarios = respuesta
        }
        catch(error) {
           console.error(error)
        }
      }

    },
    computed: {

    }
}

</script>

<style scoped lang="css">
  h2 {
    text-align: center;
  }
</style>
