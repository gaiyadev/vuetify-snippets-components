<template>
    <div>
 <template>
       <v-container fluid>
         <v-row class="text-center">
           <v-col cols="3" sm="2" md="3"></v-col>
           <v-col cols="12" sm="8" md="6">
             <v-card elevation="11" class="pt-10">
               <h2 class="purple--text text-uppercase">{{ title }}</h2>
               <v-divider color="purple" class="mt-2"></v-divider>
               <v-form
                 @submit.prevent="onLogin"
                 ref="form"
                 v-model="valid"
                 lazy-validation
                 class="mt-10 mb-6 pr-8 pl-8 pb-8 pt-4"
               >
                 <v-text-field
                   v-model="email"
                   append-icon="mail_outline"
                   outlined
                   color="purple"
                   error-count="2"
                   :rules="emailRules"
                   label="E-mail"
                   required
                 ></v-text-field>
                 <v-text-field
                   v-model="password"
                   color="purple"
                   :rules="passwordRules"
                   :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                   @click:append="show1 = !show1"
                   :type="show1 ? 'text' : 'password'"
                   label="Password"
                   outlined
                   required
                 ></v-text-field>
 
                 <v-btn
                   x-large
                   type="submit"
                   block
                   :disabled="!valid"
                   color="purple darken-4"
                   class="mr-4 text"
                   @click="validate"
                 >
                   <span class="white--text">Login</span>
                   <v-icon light>cached</v-icon>
                 </v-btn>
               </v-form>
             </v-card>
           </v-col>
           <v-col cols="3" sm="2" md="3"></v-col>
         </v-row>
       </v-container>
     </template>
   </v-container>
 </template>
 
 <script>
 export default {
   data: () => ({
     title: "Login",
     valid: true,
     show1: false,
     show2: false,
     email: "",
     emailRules: [
       v => !!v || "E-mail is required",
       v => /.+@.+\..+/.test(v) || "E-mail must be valid"
     ],
     password: "",
     passwordRules: [
       v => !!v || "Password is required",
       v => (v && v.length >= 8) || "Password must be less than 8 characters"
     ]
   }),
 
   methods: {
     //..validate inputs
     validate() {
       this.refs.form.validate();
     },
     //Login method here
     onLogin() {
       //api call here
     }
   }
 };
 </script>
 
 <style scoped>
 </style>
 
 
        
    </div>
</template>