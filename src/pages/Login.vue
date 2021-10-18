<template>
<div class="top-card">
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
          :rules="[this.required]"
          required
          autofocus
        />
        <q-input
          id="password"
          v-model="data.body.password"
          type="password"
          label="Password"
          error="Pass is not right"
          required
          @keyup.enter="login"
        /><br>
        <q-checkbox
          id="rememberMe"
          v-model="data.rememberMe"
          label="Remember me"
        />
      </q-card-section>
      <q-card-actions>
        <q-btn
          color="primary"
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
     required () {
         console.log(this.$data);
      //return  (val && val.length > 0 || 'Input is empty')
    }
   }
  
});
</script>