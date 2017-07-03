<template>
  <div class="hello">



 <v-tabs id="mobile-tabs-3" grow light>
    <v-tabs-bar slot="activators">
      <v-tabs-slider></v-tabs-slider>
      <v-tabs-item
        v-for="i in 3"
        :key="i"
        :href="'#mobile-tabs-3-' + i"
      >
        Item {{ i }}
      </v-tabs-item>
    </v-tabs-bar>
    <v-tabs-content
      v-for="i in 3"
      :key="i"
      :id="'mobile-tabs-3-' + i"
    >
      <v-card flat>
        <v-card-text>{{ text }}</v-card-text>
      </v-card>
    </v-tabs-content>
  </v-tabs>


<v-stepper v-model="e1">
    <v-stepper-header>
      <v-stepper-step step="1" :complete="e1 > 1">Name of step 1</v-stepper-step>
      <v-divider></v-divider>
      <v-stepper-step step="2" :complete="e1 > 2">Name of step 2</v-stepper-step>
      <v-divider></v-divider>
      <v-stepper-step step="3">Name of step 3</v-stepper-step>
    </v-stepper-header>
    <v-stepper-content step="1">
      <v-card class="grey lighten-1 z-depth-1 mb-5" height="200px"></v-card>
      <v-btn primary @click.native="e1 = 2" light>Continue</v-btn>
      <v-btn flat dark>Cancel</v-btn>
    </v-stepper-content>
    <v-stepper-content step="2">
      <v-card class="grey lighten-1 z-depth-1 mb-5" height="200px"></v-card>
      <v-btn primary @click.native="e1 = 3" light>Continue</v-btn>
      <v-btn flat dark>Cancel</v-btn>
    </v-stepper-content>
    <v-stepper-content step="3">
      <v-card class="grey lighten-1 z-depth-1 mb-5" height="200px"></v-card>
      <v-btn primary @click.native="e1 = 1" light>Continue</v-btn>
      <v-btn flat dark>Cancel</v-btn>
    </v-stepper-content>
  </v-stepper>


 <v-card class="grey lighten-4 elevation-0">
    <v-card-text>
      <v-container fluid>
        <v-layout row wrap>
          <v-flex xs12 sm6>
            <v-subheader v-text="'Multiple (Chips) with persistent hint'"></v-subheader>
          </v-flex>
          <v-flex xs12 sm6>
            <v-select
              label="Select"
              :items="states"
              multiple
              chips
              dark
              hint="What are the target regions"
              persistent-hint
            ></v-select>
          </v-flex>
        </v-layout>
      </v-container>
    </v-card-text>
  </v-card>

   <v-progress-linear v-bind:indeterminate="true"></v-progress-linear>
  <v-parallax src="http://oxygennacdn3.oxygenna.com/wp-content/uploads/2015/11/18.jpg" height="300">
   <v-layout column align-center justify-center>
      <h1 class="white--text">Vuetify.js</h1>
      <h4 class="white--text">Build your application today!</h4>
    </v-layout>
  </v-parallax>


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
      users: [],
       e1: 0,
e6: [],
        e7: [],
        states: [
          'Alabama','Alaska','American Samoa','Arizona',
          'Arkansas','California','Colorado','Connecticut',
          'Delaware','District of Columbia','Federated States of Micronesia',
          'Florida','Georgia','Guam','Hawaii','Idaho',
          'Illinois','Indiana','Iowa','Kansas','Kentucky',
          'Louisiana','Maine','Marshall Islands','Maryland',
          'Massachusetts','Michigan','Minnesota','Mississippi',
          'Missouri','Montana','Nebraska','Nevada',
          'New Hampshire','New Jersey','New Mexico','New York',
          'North Carolina','North Dakota','Northern Mariana Islands','Ohio',
          'Oklahoma','Oregon','Palau','Pennsylvania','Puerto Rico',
          'Rhode Island','South Carolina','South Dakota','Tennessee',
          'Texas','Utah','Vermont','Virgin Island','Virginia',
          'Washington','West Virginia','Wisconsin','Wyoming'
        ],
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
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
