<template>
  <div class="hello">
    <div>
      <v-layout row justify-center>
    <v-dialog v-model="dialog">
      <v-btn primary light slot="activator">Open Dialog</v-btn>
      <v-card>
        <v-card-row>
          <v-card-title>User Profile</v-card-title>
        </v-card-row>
        <v-card-row>
          <v-card-text>
            <v-text-field label="Email" required></v-text-field>
            <v-text-field label="Password" type="password" required></v-text-field>
            <v-text-field label="Legal first name" required></v-text-field>
            <v-text-field label="Legal middle name" hint="example of helper text only on focus"></v-text-field>
            <v-text-field label="Legal last name" hint="example of persistent helper text"
              persistent-hint
              required
            ></v-text-field>
            <v-select
              label="Age"
              required
              :items="['0-17', '18-29', '30-54', '54+']"
            ></v-select>
            <small>*indicates required field</small>
          </v-card-text>
        </v-card-row>
        <v-card-row actions>
          <v-btn class="blue--text darken-1" flat @click.native="dialog = false">Close</v-btn>
          <v-btn class="blue--text darken-1" flat @click.native="dialog = false">Save</v-btn>
        </v-card-row>
      </v-card>
    </v-dialog>
  </v-layout>
    </div>
    <div>
      <v-card v-for="user in users" class="blue darken-1 white--text mt-3">
      <v-card-text>
        <div>{{ user.name }}</div>
        <div>{{ user.email }}</div>
      </v-card-text>
    </v-card>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      users: []
    }
  }, 
  mounted(){
    this.load()
  },
  methods: {
    load(){
      fetch('https://jsonplaceholder.typicode.com/users')
      .then(res => res.json())
      .then(users =>{
        this.users = users
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
