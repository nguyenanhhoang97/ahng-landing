<template>
  <v-app dark>
    <app-header
      :menus="menus"
      :menuButtonColor="menuButtonColor"
      :headerColor="headerColor"
      :headerBackgroundSrc="headerBackgroundSrc"
      :headerTitle="headerTitle"
      :headerFixed="headerFixed"
      :footerFixed="footerFixed"
    />
    <v-main>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-main>
    <app-footer :siteCreator="footerSiteCreator" />
  </v-app>
</template>

<script>
import AppHeader from '@/components/AppHeader'
import AppFooter from '@/components/AppFooter'

export default {
  components: {
    AppHeader,
    AppFooter,
  },
  data() {
    return {
      menus: [
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
      menuButtonColor: '#41B883',
      headerColor: '#35495E',
      headerBackgroundSrc: 'https://source.unsplash.com/random',
      headerTitle: 'Nguyen Anh Hoang | ahng.xyz',
      headerFixed: true,
      footerSiteCreator: 'ahng.xyz',
      footerFixed: true,
    }
  },
}
</script>

<style lang="scss" scoped>
</style>