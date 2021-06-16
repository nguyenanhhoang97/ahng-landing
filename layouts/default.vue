<template>
  <v-app dark>
    <v-app-bar
      color="#35495E"
      dark
      shrink-on-scroll
      prominent
      src="https://source.unsplash.com/random"
      fade-img-on-scroll
      :absolute="!fixed"
      app
    >
      <v-toolbar-title v-text="title" />
      <template v-slot:extension>
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
            <v-btn v-model="fab" color="#41B883" dark fab>
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
      </template>
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <nuxt />
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
      fixed: true,
      collapseOnScroll: true,
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
      direction: 'right',
      fab: false,
      hover: false,
      top: true,
      right: false,
      bottom: false,
      left: true,
      transition: 'slide-y-reverse-transition',
    }
  },
}
</script>

<style lang="scss" scoped>
/* This is for documentation purposes and will not be needed in your application */
.v-speed-dial {
  position: absolute;
}

.v-btn--floating {
  position: relative;
}
</style>