<template>
    <div>
        <q-card
        square
        style="width: 400px; padding:50px"
        >
        <q-card-section>
            <div class="text-h6">
                Register member
            </div>
        </q-card-section>

        <q-card-section>
            <q-input
            id="email"
            v-model.trim="data.body.email"
            type="text"
            label="Email"
            bottom-slots
            required
            autofocus
            error="Email is invalid"
            />
            <q-input
            v-model.trim="data.body.name"
            type="text"
            label="Full name"
            required
            error=""
            />
            <q-input
            id="password"
            v-model="data.password"
            type="password"
            label="Password"
            bottom-slots
            required
            error= "Password is not right format"
            />
            <q-input
            id="repeatPassword"
            v-model="data.body.repeatPassword"
            type="password"
            label="Repeat Password"
            bottom-slots
            required
            errore="Password is not match"
            />
        </q-card-section>
        <q-card-actions>
            <q-btn
            color="primary"
            label="Register"
            @click="register"
            />
        </q-card-actions>
        </q-card>
    </div>
</template>

<script lang="ts">
import { defineComponent} from 'vue';

export default defineComponent({
  name: 'RegisterContainer',
  data () {
    return {
      data: {
        body: {
            name: '',
            email: '',
            password: '',
            repeatPassword: ''
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
