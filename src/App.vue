<template>
<div>
<LoginForm 
v-if="!Loggedin" 
:onLogin="handleLogin" 
/>


<div v-else class="grid">
<DataForm
  v-for="(item, key) in items"
  :key="key"
  :item="item"
/>
</div>

</div>
</template>

<script>
import LoginForm from "./components/LoginForm.vue"
import DataForm from "./components/DataForm.vue";

export default {
  name: 'App',
  components: {
    LoginForm,
    DataForm
  },
data(){
  return{
    Loggedin: false,
    items: []
  }
},
methods: {
  handleLogin(){
    this.Loggedin = true
 fetch("https://cis255.vercel.app/api", {method: "POST", headers: {"Content-Type": "application/json"}, body: JSON.stringify({ password: "cardinals" })
})

  .then(res => res.json())
  .then(data => { this.items = data.books })


  }
}

}
</script>

<style>
  .grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 12px;
}
.TBox {
background-color: green;
border: 2px solid green;
padding: 10px;  
}

.FBox {
background-color: red;
border: 2px solid red;
padding: 10px;
}
</style>
