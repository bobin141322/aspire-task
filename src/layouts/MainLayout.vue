<template>
  <q-layout view="lHh Lpr lFf" class="page-layout">
    <q-page-container class="container">
           <q-toolbar class="toolbar">
              <q-btn flat round dense icon="menu" class="q-mr-sm" />
            
              <q-btn flat round dense icon="whatshot" />
          </q-toolbar>
           <q-drawer
            v-model="drawer"
            show-if-above
            :width="200"
            :breakpoint="500"
            bordered
            class="bg-grey-3 mobile-navigation"
          >
            <q-scroll-area class="fit">
              <q-list>
                 <EssentialLink class="menu-nav"
                    v-for="link in essentialLinks"
                    :key="link.title"
                    v-bind="link"
                  />
              </q-list>
            </q-scroll-area>
          </q-drawer>
          <div class="navigation col-3">
            <q-list>
              <q-item-label
                header
              >
               <div class="aspire-logo"></div>
               <p class="slogan">Trusted way of banking for 3,000+ SMEs and startups in Singapore</p>
              </q-item-label>
              
              <EssentialLink class="menu-nav"
                v-for="link in essentialLinks"
                :key="link.title"
                v-bind="link"
              />
            </q-list>
          </div>
          <div class="content-page col-9">
            <router-view />
          </div>

   
    </q-page-container>

    <!-- <div class='comments-list-wrapper bordered right'>
        
    </div> -->

  </q-layout>
</template>

<script lang="ts">
import EssentialLink from 'components/EssentialLink.vue'
// import CardComponent from 'components/CardComponent.vue'

const linksList = [
  {
    title: 'Home',
    icon: 'aspire-icon',
    link: 'home'
  },
  {
    title: 'Card',
    icon: 'card-icon',
    link: 'card'
  },
  {
    title: 'Payment',
    icon: 'payment-icon',
    link: 'payment'
  },
  {
    title: 'Credit',
    icon: 'credit-icon',
    link: 'credit'
  },
  {
    title: 'Setting',
    icon: 'account-icon',
    link: 'setting'
  }
];

import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      drawer: ref(false),
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  },
  
})
</script>
