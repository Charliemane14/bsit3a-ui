<template>

  <div class="container">
    
    <v-card class="form elevation-2">
      <div class="logo"><img src="@/static/maple.png" alt="Logo" class="logo-img"></div>
      <div class="sociallink">


        <v-row class="mx-12 mt -5">

          <v-col cols="auto" class="mr-auto">
            <v-btn outlined color="blue-grey">
              <v-icon color="red" left>mdi-google</v-icon>GOOGLE</v-btn>
          </v-col>

          <v-col cols="auto">
            <v-btn outlined color="blue-grey">
              <v-icon color="blue" left>mdi-facebook</v-icon>FACEBOOK</v-btn>
          </v-col>

        </v-row>
      </div>

      <v-card-text>
        <v-form ref="form" v-model="valid" lazy-validation>


          <v-text-field v-model="email" :rules="emailRules" label="E-mail" required prepend-inner-icon="mdi-account"
            outlined>
          </v-text-field>

          <v-text-field v-model="password" :rules="passwordRules" label="Pasword" required type="password"
            prepend-inner-icon="mdi-lock" outlined>
          </v-text-field>

          <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate" block>
            LOGIN
          </v-btn>

        </v-form>       
      </v-card-text>

      <div class="Submit" @click="validate">
        <a href="/signup">
        <v-btn text style="color: blue; font-size: 13px;">
        Create an Account
        </v-btn>
      </a>
      </div>
      
      <div class="Submit2">
        <v-btn text style="color: blue; font-size: 13px;">
          Forgot Password?
        </v-btn>
      </div>

    </v-card>
  </div>



</template>


<script>
export default {
  layout: 'auth',

  name: 'IndexPage',
  data: () => ({
    valid: true,
    password: '',
    passwordRules: [
      v => !!v || 'Password is required',
      v => (v && v.length <= 50) || 'Name must be less than 50 characters',
    ],
    email: '',
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ],

  }),
  methods: {
    validate() {
      if (this.$refs.form.validate()) {
        console.log("Logging In");
        this.$router.push("/dashboard");
      }
    }
  }
}
</script>

<style>
.Submit{
  display: flex;
  text-decoration: underline;
  color: blue;
  
}

.Submit2{
  display: flex;
  text-decoration: underline;
  color: blue;
}

.container {
  
  display: flex;
  align-items: center;
  flex-direction: column;
  height: 80%;
  width: 80%;
  
}

.form {

  height: 800px;
  width: 500px;
  margin-top: 100px;
  border-radius: 10px;

}

.logo {

  display: flex;
  align-items: center;
  flex-direction: column;
  width: 100%;
  height: 200px;

}

.logo-img {

  height: 150px;
  margin-top: 50px;
}

.sociallink {

  display: flex;
  align-items: center;
  justify-content: space-around;
  height: 100px;
  width: 100%;
}

.btn-google {
  border-color: blue;
  border-width: 1px;
}

</style>
