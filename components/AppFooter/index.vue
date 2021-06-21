<template>
  <v-footer :absolute="!footerFixed" app>
    <span>&copy; {{ new Date().getFullYear() }} {{ siteCreator }}</span>
  </v-footer>
</template>

<script>
export default {
  props: ['siteCreator', 'footerFixed'],
}
</script>

<style lang="scss" scoped>
@import './styles.scss';
</style>