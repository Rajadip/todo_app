<template>
  <div id="app">
    <router-link v-if="authenticated" to="/login" type="button" v-on:click.native="logout()" replace>Logout</router-link>
    <router-view @authenticated="setAuthenticated" />
  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
<script>
  export default{
    name:'App',
    data() {
            return {
                authenticated: false,
            }
        },
    mounted() {
            if(!this.authenticated) {
                this.$router.replace({ name: "login" });
            }
        },
    methods:{
            setAuthenticated(status) {
                this.authenticated = status;
            },
            logout() {
                this.authenticated = false;
            }
    }
  }
</script>