<template>
  <v-app>

    <v-dialog v-model="dialogContact" max-width="600px"> 
      <v-card>
        <v-layout align-center justify-center>
          <v-card-title class="green darken-4 mt-4 mb-4 white--text" style="font-weight: 600; border-radius: 5px;">Kontak Kami</v-card-title>
        </v-layout>
        <v-card-text>
          <span color="green darken-2" style="font-weight: 600;">Memiliki pertanyaan? isi form dibawah dan langsung hubungi kami!</span>
          <v-form @submit.prevent="submitForm">
            <v-text-field v-model="name" label="Nama" outlined></v-text-field>
            <v-text-field v-model="email" label="Email" outlined></v-text-field>
            <v-textarea v-model="message" label="Pesan" outlined></v-textarea>
            <v-btn type="submit" color="primary">Kirim</v-btn>
            <v-btn @click="dialogContact = false" color="error">Batal</v-btn>
          </v-form>
        </v-card-text>
      </v-card>
    </v-dialog>

    <v-toolbar max-height="64" class="white" elevation="4" fixed>
      <v-toolbar-title style="padding: 5px; color: #1B5E20; font-weight: 800;">PaneninJualin</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <template v-for="(item, index) in toolbarList">
          <v-btn color="white" elevation="0" style="color: #1B5E20; font-weight: 600;" :to="item.to">{{ item.name }}</v-btn>
        </template>
        <v-btn color="green darken-2" elevation="0" style="color: white; font-weight: 600;" @click="dialogContact = true">Kontak</v-btn>
      </v-toolbar-items>
    </v-toolbar>

    <v-main>
      <Nuxt />
    </v-main>
    
    <v-footer light padless bottom>
      <v-card flat tile class="green darken-4 white--text text-center">
        <v-card-text>
          <v-btn class="white--text" icon href="https://github.com/orgs/PaneninJualin-C23M4039" target="_blank">
            <v-icon size="30px">
              mdi-github
            </v-icon>
          </v-btn>
        </v-card-text>

        <v-card-text class="white--text pt-0">
          PaneninJualin adalah sebuah aplikasi yang didesain khusus untuk membantu petani dalam mendistribusikan hasil panen mereka dengan lebih efisien. 
          Aplikasi ini memungkinkan petani untuk menjual produk pertanian mereka secara langsung kepada konsumen atau pembeli potensial melalui platform online. 
          Dengan fitur-fitur seperti 'Jualin', dan 'Informasi', 
          PaneninJualin memberikan kemudahan bagi petani untuk meningkatkan akses pasar dan meningkatkan pendapatan mereka. Dengan demikian, 
          aplikasi ini dapat membantu untuk memperkuat rantai pasok pertanian dan mendukung pertumbuhan ekonomi petani.
        </v-card-text>

        <v-divider color="white"></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>PaneninJualin</strong>
        </v-card-text>
      </v-card>
    </v-footer>

  </v-app>
</template>

<script>
export default {
  name: 'LandingLayout',
  data() {
    return {
      toolbarList: [
        { name: 'Home', to: '/' },
        { name: 'Jualin', to: '/jualin' },
        { name: 'Panenin', to: '/informasi' },
        { name: 'Tentang Kami', to: '/tentangKami' },
      ],
      dialogContact: false,
    }
  },
  methods() {

  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter&display=swap');

* {
  scroll-behavior: smooth;
  font-family: 'Inter', sans-serif !important;
}

</style>