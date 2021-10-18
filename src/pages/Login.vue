<template>
<div class="login-page">
<q-card
      square
      style="width: 400px; padding:50px"
    >
      <q-card-section>
        <div class="text-h6">
            Login Page
        </div>
      </q-card-section>

      <q-card-section>
        <q-input
          id="email"
          v-model.trim="data.body.email"
          type="email"
          label="Email address"
          error="Email is not right"
          :rules="[this.required, this.isEmail]"
          required
          autofocus
        />
        <q-input
          id="password"
          v-model="data.body.password"
          type="password"
          label="Password"
          error="Please check email and password"
          required
           :rules="[this.required]"
          @keyup.enter="login"
        /><br>
        <q-checkbox
          id="rememberMe"
          v-model="data.rememberMe"
          label="Remember me"
        />
      </q-card-section>
      <q-card-actions>
         <router-link to="/register" class="link-button">
          Register
        </router-link>
        <q-btn
          @click="login"
        >
          Login
        </q-btn>
      </q-card-actions>
      <router-link to="/password/forgot">
        <!-- <a>{{ this.$t('auth.login.password_forgot') }}</a> -->
      </router-link>
    </q-card>
</div>
</template>


<script lang="ts">
import { defineComponent} from 'vue';

export default defineComponent({
  name: 'LoginContainer',
  data () {
    return {
      data: {
        body: {
          email: '',
          password: ''
        },
        rememberMe: false
      },
      loading: false
    }
  },
   methods: {
     required (element: string) {
         console.log(this.$data);
         const isNull = !element? false : true;
         return isNull;
      //return  (val && val.length > 0 || 'Input is empty')
    },
     isEmail (element: string) {
       const emailPattern = /^(?=[a-zA-Z0-9@._%+-]{6,254}$)[a-zA-Z0-9._%+-]{1,64}@(?:[a-zA-Z0-9-]{1,63}\.){1,8}[a-zA-Z]{2,63}$/
       return (emailPattern.test(element) || 'Invalid email')
     },
    login () {
      alert('login sucess')
    }
   }
  
});
</script>