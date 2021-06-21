<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card>
        <v-card-text>
          <div>ahng.xyz</div>
          <p class="text-h4 text--primary">under·construction</p>
          <div class="text--primary">Đang làm. Bao giờ xong nó sẽ xong</div>
        </v-card-text>
        <v-divider class="mx-4"></v-divider>
        <v-card-actions class="social-part">
          <v-btn fab x-small color="#BF211E" @click="socialNavigate('gmail')">
            <v-icon dark> mdi-gmail </v-icon>
          </v-btn>
          <v-btn
            fab
            x-small
            color="#1773EA"
            @click="socialNavigate('facebook')"
          >
            <v-icon dark> mdi-facebook </v-icon>
          </v-btn>
          <v-btn
            fab
            x-small
            color="#BF27A0"
            @click="socialNavigate('instagram')"
          >
            <v-icon dark> mdi-instagram </v-icon>
          </v-btn>
          <v-btn fab x-small color="#302F2F" @click="socialNavigate('github')">
            <v-icon dark> mdi-github </v-icon>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>

export default {
  methods: {
    socialNavigate: (type) => {
      switch (type) {
        case 'gmail':
          location.href = 'mailto:nguyenanhhoang.ict@gmail.com'
          break
        case 'facebook':
          location.href = 'https://www.facebook.com/anhhoang.ahng'
          break
        case 'instagram':
          location.href = 'https://www.instagram.com/ahng._'
          break
        case 'github':
          location.href = 'https://github.com/nguyenanhhoang97'
          break
        default:
          return
      }
    },
  },
}
</script>

<style lang="scss" scoped>
.v-card__actions {
  margin-left: 0.4rem;
}
</style>
