<template>
	<div id="Login" >
		<h3>Login</h3>
		<form>
			<div class="form-group">
				<div class="input-group mb-3">
					<div class="input-group-prepend">
						<span class="input-group-text" id="basic-addon1">@</span>
					</div>
					<input type="text" class="form-control" name="username" v-model="input.username" placeholder="Username" />
				</div>
				<div class="input-group mb-3">
					<div>
						<input type="password" class="form-control" name="password" v-model="input.password" placeholder="Password" />
					</div>
				</div>
				<div><input type="Submit" class="btn btn-primary" v-on:click="login()" name="Submit" value="Submit" /></div>
			</div>
		</form>
	</div>
</template>
<script>
	import axios from "axios";
	export default {
		name:'Login',
		data() {
			return {
				input: {
                    username: "",
                    password: ""
                },
                response: {

                }

            }
        },
		methods:{
			login(){
				axios.post('http://127.0.0.1:5000/login')
					.then(res => {this.response = res})
					.catch(error => {console.log(error);})
				console.log(this.response)
				console.log("Login Clicked ...."+this.input.username)
				this.$emit("authenticated", true);
				this.$router.replace({ name: "home" });
			}
		}
	}
</script>