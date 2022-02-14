<template>
  <h1 class="my-5">Registro de usuarios</h1>
  <form>
    <!-- .trim se usa para limpiar espacios en blanco -->
    <input
      type="email"
      placeholder="email"
      class="form-control my-2"
      v-model.trim="email"
    />

    <input
      type="password"
      placeholder="password"
      class="form-control my-2"
      v-model.trim="pass1"
    />

    <input
      type="password"
      placeholder="password"
      class="form-control my-2"
      v-model.trim="pass2"
    />

    <button type="submit" class="btn btn-primary" :disabled="bloquear">
      Registrar
    </button>
  </form>
</template>

<script>
export default {
  //Uso de vdata para capturar el email y el password
  data() {
    return {
      email: "",
      pass1: "",
      pass2: "",
    };
  },
  computed: {
    bloquear() {
      if (!this.email.includes("@")) {
        return true
      }
      if (this.pass1.length > 5 && this.pass1 === this.pass2) {
        return false
      }
      return true
    }
  }
};
</script>
