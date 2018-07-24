<template>
  <div id="app">
    <v-app  id="inspire">
      <v-navigation-drawer fixed v-model="sideNav" app>
        <v-list>
          <v-list-tile v-for="item in menuItems" :key="item.title">

            <v-list-tile-action>
              <v-icon>{{item.icon}}</v-icon> 
            </v-list-tile-action>
            <v-list-tile-content>
              {{item.title}}
            </v-list-tile-content>


          </v-list-tile>
        </v-list>
      </v-navigation-drawer>
      <!-- ================================== -->
      <v-toolbar dark class="primary">
          <span class="hidden-sm-and-up"> <v-toolbar-side-icon @click="sideNav=!sideNav"></v-toolbar-side-icon> </span>
          
          <!-- ************ -->
          <v-toolbar-title>DevMeetup</v-toolbar-title>
          <!-- ************ -->
          <v-spacer></v-spacer>
          <!-- ************ -->
          <v-toolbar-items class="hidden-xs-only">
              <v-btn flat v-for="item in menuItems" :key="item.title">
                <v-icon left dark>{{item.icon}}</v-icon> {{item.title}}
              </v-btn>
          </v-toolbar-items> 
          <!-- ************ -->
      </v-toolbar>
      <!-- ================================== -->
      <main>
        <router-view></router-view>
      </main>
    </v-app>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        sideNav: null,
        menuItems: [
          { icon: 'supervisor_account', title: 'View Meetups' },
          { icon: 'room', title: 'Organize Meetups' },
          { icon: 'person', title: 'Profile' },
          { icon: 'face', title: 'Sign Up' },
          { icon: 'lock_open', title: 'Sign In' }
        ]

      }
    }
  }
</script>

<style lang="stylus">
  @import './stylus/main'
</style>
