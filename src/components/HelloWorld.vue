<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/logo.png')"
          class="my-3"
          contain
          height="200"
        />
        <h2>Ingrese su credencial</h2>
      </v-col>
    </v-row>
    <v-row class="text-center">
      <v-col cols="12">
        <form action="">
          <div class="cja">
            <v-text-field
              :rules="rules"
              hide-details="auto"
            ></v-text-field>
          </div>
          <br />
          <br />
          <v-btn text @click="insertarRuta('/about')"><span class="mr-2">Ingresar</span></v-btn>
        </form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",

  data: () => ({
    rules: [
      (value) => !!value || "Campo Requerido.",
      (value) =>
        (value && value.length >= 10) ||
        "Su Identificacion consta de 10 digitos",
        
    ],
  }),
  methods:{
  insertarRuta(ruta){
    this.$router.push(ruta);
  }
 }
};
</script>

<style scoped>
.my-3 {
  width: 20%;
  margin: auto;
}
.cja{
  width: 10%;
  margin: auto;
}
</style>