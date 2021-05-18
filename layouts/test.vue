<template>
<v-app dark>
  <v-main app>
        <v-toolbar color="transparent" fixed class="mytoolbar elevation-4"> 
          <!--This is menu bar -->
      <!-- <v-toolbar-title v-text="title"></v-toolbar-title> -->
     
          <!--mega menu 1, the open-on-hover help to display the child menu inside the first menu item -->
      <v-menu open-on-hover offset-y class="menuspacefirst">
        <template v-slot:activator="{ on, attrs }">
          <p color="primary" 
          dark 
          v-bind="attrs"
          v-on="on">
          Our Services
          </p>
        </template>
      <v-list>
        <v-list-tile v-for="(item, index) in services" :key="index">
          <v-list-tile-title>{{ item.title }}</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-menu>
    <v-menu open-on-hover offset-y class="menuspace">
              <template v-slot:activator="{ on, attrs }">
          <p color="primary" 
          dark 
          v-bind="attrs"
          v-on="on">
        Developers</p>
        </template>
      <v-list>
        <v-list-tile v-for="(item, index) in developers" :key="index">
          <v-list-tile-title>{{ item.title }}</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-menu>
    <v-menu open-on-hover offset-y class="menuspace">
                    <template v-slot:activator="{ on, attrs }">
          <p color="primary" 
          dark 
          v-bind="attrs"
          v-on="on">
        Company</p>
        </template>
      <v-list>
        <v-list-tile v-for="(item, index) in company" :key="index">
          <v-list-tile-title>{{ item.title }}</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-menu>
    <v-menu offset-y class="menuspace">
        <p slot="activator" color="primary" dark> Pricing</p>
    </v-menu>
    <v-menu offset-y class="menuspace">
        <p slot="activator" color="primary" dark> Support</p>
    </v-menu>
    <v-menu offset-y class="menuspace">
        
      <p slot="activator" color="primary" dark><v-icon>
account_circle
</v-icon> Sign in </p>
    </v-menu>
    </v-toolbar>
    <Nuxt />
  </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    services: [
      { title: 'Click Me' },
      { title: 'Click Me' },
      { title: 'Click Me' },
      { title: 'Click Me 2' }
    ],
    developers: [
      { title: 'Click Me' },
      { title: 'Click Me' },
      { title: 'Click Me' },
      { title: 'Click Me 2' }
    ],
    company: [
      { title: 'Click Me' },
      { title: 'Click Me' },
      { title: 'Click Me' },
      { title: 'Click Me 2' }
    ]
  }),
  components: {
    CoreAppBar: () => import('@/components/core/AppBar'),
    CoreSystemBar: () => import('@/components/core/SystemBar'),
    CoreFooter: () => import('@/components/core/Footer'),
  }
}
</script>
<style scoped lang="scss">
 .mytoolbar
 {
     padding: 30px;
     margin-left: 180px;
 }
 .menuspace
 {
     margin-left: 70px;
     font-size: 13pt;
 }
 .menuspacefirst
 {
     margin-left: 160px;
     font-size: 13pt;
 }

</style>
