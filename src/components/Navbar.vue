<template>
    <!-- Navbar -->
  <nav class="navbar navbar-expand-lg navbar-dark ps-5" style="background-color: black;">
    <div class="container-fluid">
      <a class="navbar-brand" >E-COMMERCE CMS</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div v-if="isLogin" class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <router-link to="/" class="nav-link active" aria-current="page" >Home</router-link>
          </li>
        </ul>

        <router-link to="/add" class="btn btn-light btn-sm mt-1 me-3" style="font-weight: bold;">Add Product</router-link>
        <button @click.prevent="logout" class="btn btn-dark btn-sm mt-1 me-3" style="background-color: red; font-weight: bold;">Logout</button>

      </div>
    </div>
  </nav>
  <!-- Navbar -->
</template>

<script>
export default {
  name: 'Navbar',
  methods: {
    toAddForm () {
      this.$router.push('add')
    },
    logout () {
      localStorage.clear()
      this.$router.push('login')
    }
  },
  computed: {
    isLogin () {
      return this.$route.name !== 'Login'
    }
  }
}
</script>

<style>

</style>
