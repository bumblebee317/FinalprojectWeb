<template>
<div>
 <h2>Login</h2>
<input v-model="password" placeholder="Enter Password">
<button @click="checkpass">
Login
</button>
<p>Password: cardinals</p>
</div>
</template>

<script>
export default {
    props: ["onLogin"],
    data(){
        return {
            password: "cardinals"
        }
    },
methods: {
    checkpass() {
        if(this.password === "cardinals"){
            this.onLogin()
        } else {
            alert("Wrong Password")
        }
    }
}



}



</script>