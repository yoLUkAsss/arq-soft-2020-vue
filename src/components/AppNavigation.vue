<template>
    <span>
        <v-navigation-drawer app v-model="drawer" class="brown lighten-2" dark disable-resize-watcher>
            <v-list>
              <v-subheader> Insumos App </v-subheader>
              <v-list-item-group color="primary">
                <v-list-item v-for="(item, index) in items" :key="index">
                    <v-list-item-content>
                        <v-list-item-title @click="go(item.page)"> {{item.title}} </v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
                <v-divider v-for="(item, index) in items" :key="`divider-${index}`"></v-divider>
              </v-list-item-group>
            </v-list>
        </v-navigation-drawer>
        <v-app-bar app color="brown darken-4" dark>
            <v-app-bar-nav-icon class="hidden-md-and-up" @click="clickDrawer"></v-app-bar-nav-icon>
            <v-spacer class="hidden-md-and-up"></v-spacer>
            <v-btn class="hidden-sm-and-down" @click="clickDrawer">Menu</v-btn>
            <v-spacer class="hidden-sm-and-down"></v-spacer>
            <v-btn class="hidden-sm-and-down" @click="goLogin">Log In</v-btn>
            <v-btn color="brown lighten-3" class="hidden-sm-and-down" @click="goRegister"> Register</v-btn>
        </v-app-bar>
    </span>
</template>

<script>
export default {
  name: 'AppNavigation',
  data () {
    return {
      drawer: false,
      items: [
        { title: 'Home', page: 'Home' },
        { title: 'Log In', page: 'Login' },
        { title: 'Register', page: 'SignUp' },
        { title: 'Users', page: 'Users' }
      ]
    }
  },
  methods: {
    goRegister () {
      this.$router.push({ name: 'SignUp' })
    },
    goLogin () {
      this.$router.push({ name: 'Login' })
    },
    go (page) {
      this.$router.push({ name: page })
    },
    clickDrawer () {
      this.drawer = !this.drawer
    }
  }
}
</script>

<style scoped>

</style>
