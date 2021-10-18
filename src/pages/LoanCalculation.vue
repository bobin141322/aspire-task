<template>
    <div class="loan-page">
        <div class="loan-container">
        <p class="ins">
        Enter your values to see your monthly payment, and grand total, and interest paid.
        </p>

        <div class="columns">
  
            <div class="column">    
                <label>Principal Loan Amount</label>
                <q-input class="input" type="number" :blur="calc" v-model.number="loan.principal"/>
            </div>
            <div class="column">    
                <label>Interest Rate</label>
                <q-input class="input" type="text" :blur="calc" v-model.number="loan.interest"/>
            </div>
            <div class="column">    
                <label>Time in Years</label>
                <q-input class="input" type="number" :blur="calc" v-model.number="loan.timeYears"/>
            </div>
            <div class="column">    
                <label>Compounded (months)</label>
               <q-input class="input" type="number" :blur="calc" v-model.number="loan.compoundingEvery"/>
            </div>
        </div>
        <q-btn
          @click="calc"
        >
         Calculate
        </q-btn>

        <div class="result-columns">
        <div class="column">
            <div class="notification is-success">
            <h3>Monthly Payment</h3>
            <p>${{ formatPrice(loan.payment) }}</p>
            </div>
        </div>
        <div class="column">
            <div class="notification is-warning">
            <h3>Grand Total</h3>
            <p>${{ formatPrice(loan.total) }}</p>
            </div>
        </div>
        <div class="column">
            <div class="notification is-danger">

            <h3>Total Interest</h3>
            <p>${{ formatPrice(loan.totalInterest) }}</p>
            </div>
        </div>
        </div>
    </div>
    </div>
</template>

<script lang="ts">
import { defineComponent} from 'vue';

export default defineComponent({
  name: 'LoanContainer',
  data() {
      return {
        loan: {
                principal: 300000,
                interest: .0299,
                compoundingEvery: 12,
                timeYears: 15,
                payment: 0,
                total: 0,
                totalInterest: 0,
                l: 0,
                r: 0
                }
            }
      }
    ,
    methods: {
        calc: function () {
            let loan = this.$data.loan;
            loan.l =  loan.principal*((1+ (loan.interest/loan.compoundingEvery))**(loan.compoundingEvery*loan.timeYears));
            loan.r = (((1+ (loan.interest/loan.compoundingEvery))**(loan.compoundingEvery*loan.timeYears))-1)/(loan.interest/loan.compoundingEvery);
            loan.payment = Math.round(loan.l / loan.r * 100) /100 ;
            loan.total = Math.round(loan.payment * loan.compoundingEvery*loan.timeYears  * 100) /100 ;
            loan.totalInterest = Math.round((loan.total - loan.principal )  * 100) /100 ;
            
        },
        formatPrice(value:number) {
            let val = (value/1).toFixed(2);
            return val.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
        }
    }
});
</script>