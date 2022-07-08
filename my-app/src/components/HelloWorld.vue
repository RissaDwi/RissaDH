<template>
<v-app>
      <div class="background"></div>
      <v-main class="d-flex justify-center align-center">
        <v-col cols="10" lg="4" class="mx-auto">
          <v-card class="pa-4">
             <div class="text-center">
               <v-avatar size="100" color="indigo lighten-4">
                  <v-icon size="40" color="indigo"> mdi-account</v-icon>
               </v-avatar>
                <h2>Welcome</h2>
             </div>
             <v-form @submit.prevent="submitHandler" ref="form">
               <v-card-text>
                 <v-text-field
                  v-model="username"
                  :rules="usernameRules"
                  type="username"
                  label="username"
                  placeholder="username"
                  prepend-inner-icon="mdi-account"
                  required/>
                 <v-text-field
                  v-model="password"
                  :rules="passwordRules"
                  :type="passwordShow ? 'text' : 'password'"
                  label="password"
                  placeholder="password"
                  prepend-inner-icon="mdi-key"
                  :append-icon="passwordShow ? 'mdi-eye' : 'mdi-eye-off'"
                  @click:append="passwordShow = !passwordShow"
                  required/>
               </v-card-text>
               <v-card-action class="justify-center">
                 <v-btn :loading="loading" color="indigo" type="submit">
                <span class="white--text px-12"> Login</span>
              </v-btn>
               </v-card-action>
             </v-form>
          </v-card>
        </v-col>
      </v-main>
  </v-app>
</template>

<script>
// export default {
//   name: 'HelloWorld',
//   props: {
//     msg: String
//   }
// }
export default {
  name: "HelloWorld",
  data: () => ({
    // loading: false,
    // snackbar: false,
    passwordShow: false,
    username: "",
    usernameRules: [(v) => !!v || "Username is required"],
    password: "",
    passwordRules: [
      (v) => !!v || "Password is required",
      (v) => (v && v.length >= 8) || "Password must be 8 character",
    ],
  }),

  methods: {
    submitHandler() {
      // console.log("sukses");
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
