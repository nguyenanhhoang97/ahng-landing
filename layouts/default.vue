<template>
  <v-app dark>
    <v-app-bar
      absolute
      color="#6A76AB"
      dark
      shrink-on-scroll
      prominent
      src="https://picsum.photos/1920/1080?random"
      fade-img-on-scroll
      fixed
      app
      :clipped-left="clipped"
    >
      <!-- <v-app-bar-nav-icon @click.stop="drawer = !drawer" /> -->
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
        <v-speed-dial
          v-model="fab"
          :top="top"
          :bottom="bottom"
          :right="right"
          :left="left"
          :direction="direction"
          :open-on-hover="hover"
          :transition="transition"
        >
          <template v-slot:activator>
            <v-btn v-model="fab" color="blue darken-2" dark fab>
              <v-icon v-if="fab"> mdi-hexagon-multiple </v-icon>
              <v-icon v-else> mdi-hexagon-multiple-outline </v-icon>
            </v-btn>
          </template>
          <v-btn
            v-for="(item, i) in items"
            :key="i"
            :to="item.to"
            router
            exact
            fab
            small
            :color="item.color"
          >
            <v-icon>{{ item.icon }}</v-icon>
          </v-btn>
        </v-speed-dial>
      </v-container>
    </v-main>

    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }} ahng.xyz</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-home-roof',
          title: 'Welcome',
          to: '/',
          color: 'green',
        },
        {
          icon: 'mdi-heart',
          title: 'Inspire',
          to: '/inspire',
          color: 'indigo',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Nguyen Anh Hoang | ahng.xyz',
      direction: 'top',
      fab: false,
      hover: false,
      top: false,
      right: true,
      bottom: true,
      left: false,
      transition: 'slide-y-reverse-transition',
    }
  },
}
</script>

<style>
/* This is for documentation purposes and will not be needed in your application */
.v-speed-dial {
  position: absolute;
}

.v-btn--floating {
  position: relative;
}
</style>