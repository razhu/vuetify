<template>
  <div class="hello">

<v-layout justify-space-around>
    <v-icon large class="green--text text--darken-2">business</v-icon>

    <v-icon large class="orange--text text--darken-2">chat</v-icon>

    <v-icon large class="purple--text text--darken-2">dialpad</v-icon>

    <v-icon large class="teal--text text--darken-2">email</v-icon>

    <v-icon large class="blue-grey--text text--darken-2">call_split</v-icon>

    <v-icon large class="orange--text text--darken-2">present_to_all</v-icon>
  </v-layout>



   <div class="text-xs-center">


<v-chip class="primary white--text">Primary</v-chip>

    <v-chip class="secondary white--text">Secondary</v-chip>

    <v-chip class="red white--text">Colored Chip</v-chip>

    <v-chip class="green white--text">Colored Chip</v-chip>

    <v-chip class="indigo white--text">
      <v-avatar>
        <v-icon>account_circle</v-icon>
      </v-avatar>
      Ranee
    </v-chip>

    <v-chip class="orange white--text">
      Premium
      <v-icon right>star</v-icon>
    </v-chip>

    <v-chip class="primary white--text">
      1 Year
      <v-icon right>cake</v-icon>
    </v-chip>

    <v-chip class="green white--text">
      <v-avatar class="green darken-4">1</v-avatar>
      Years
    </v-chip>

    <v-chip close class="teal white--text">
      <v-avatar>
        <v-icon>check_circle</v-icon>
      </v-avatar>
      Confirmed
    </v-chip>
  </div>
    <div>
        <v-layout justify-space-around>
    <v-icon dark>home</v-icon>

    <v-icon dark>event</v-icon>

    <v-icon dark>info</v-icon>

    <v-icon dark>folder_open</v-icon>

    <v-icon dark>widgets</v-icon>

    <v-icon dark>gavel</v-icon>
  </v-layout>
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
<style scoped>

</style>
