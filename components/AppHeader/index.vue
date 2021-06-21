<template>
  <v-app-bar
    :color="headerColor"
    dark
    shrink-on-scroll
    prominent
    :src="headerBackgroundSrc"
    fade-img-on-scroll
    :absolute="!headerFixed"
    app
  >
    <v-toolbar-title v-text="headerTitle" />
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
          <v-btn v-model="fab" :color="menuButtonColor" dark fab>
            <v-icon v-if="fab"> mdi-hexagon-multiple </v-icon>
            <v-icon v-else> mdi-hexagon-multiple-outline </v-icon>
          </v-btn>
        </template>
        <v-btn
          v-for="(item, i) in menus"
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
</template>

<script>
export default {
  props: [
    'menus',
    'menuButtonColor',
    'headerColor',
    'headerBackgroundSrc',
    'headerTitle',
    'headerFixed',
  ],
  data() {
    return {
      clipped: false,
      drawer: false,
      collapseOnScroll: true,
      miniVariant: false,
      right: true,
      rightDrawer: false,
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
@import './styles.scss';
</style>