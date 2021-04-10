<template>
  <v-app>
    <Navbar2/>
    
    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
//import Navbar from '@/components/Navbar'
import Navbar2 from '@/components/Navbar2'
export default {
  name: 'App',

  components: {
    Navbar2,
  },

  data: () => ({
    
  }),
};
</script>
