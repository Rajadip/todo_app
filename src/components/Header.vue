<template>
  <div>
	<nav id="nav" class="navbar navbar-expand-lg navbar-light bg-light">
      <div>
        <ul class="navbar-nav mr-auto">
          <li class="nav-item">
            <router-link to="/home">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/about">About</router-link>
          </li>
        </ul>
      </div>
    </nav>
    <router-view/>
  </div>
</template>

<style scoped>
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

</style>

<script>
export default {
  name: 'Header',
}
</script>