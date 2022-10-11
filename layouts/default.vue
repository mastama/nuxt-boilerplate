<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="sideDrawer"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      fixed
      app>
      <v-app-bar-nav-icon @click.stop="sideDrawer = !sideDrawer" />
      <v-toolbar-title>{{ title }}</v-toolbar-title>
      <!-- <v-spacer /> -->
    </v-app-bar>

    <v-main>
      <v-container>
        <Nuxt /> <!-- bagian ini untuk menampilkan isi content -->
      </v-container>
    </v-main>

  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      sideDrawer: false,
      items: [
        {
          icon: 'mdi-application',
          title: 'App',
          to: '/'
        },
        {
          icon: 'mdi-account',
          title: 'Account',
          to: '/account'
        },
        {
          icon: 'mdi-bell',
          title: 'Notification',
          to: '/notification'
        }

      ],
      right: true,
      title: 'Cashier'
    }
  }
}
</script>
