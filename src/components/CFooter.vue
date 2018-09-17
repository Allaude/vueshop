<template>
  <v-footer
    dark
    height="auto"
  >
    <v-flex xs12>
    <v-card
      flat
      tile
      class="secondary darken-1 white--text text-xs-center"
    >
      <v-card-text v-if="isHome">
        <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-3 white--text"
          icon
        >
          <v-icon size="24px">{{ icon }}</v-icon>
        </v-btn>
      </v-card-text>

      <v-card-text  v-if="isHome" class="white--text pt-0">
        Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet. Mauris cursus commodo interdum. Praesent ut risus eget metus luctus accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim a sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum tempor vel ut orci. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
      </v-card-text>
      
      <v-layout
        justify-center
        row
        wrap
        >
        <v-btn
            v-for="link in links"
            :key="link"
            color="white"
            flat
            round
        >
            {{ link }}
        </v-btn>
        <v-flex
            secondary
            darken-2
            py-3
            text-xs-center
            white--text
            xs12
        >
            &copy;2018 — {{ appName }} powered by <a class="white--text" href='https://domainesia.com'><strong>Domainesia</strong></a>
        </v-flex>
        </v-layout>
    </v-card>
    </v-flex>
  </v-footer>
</template>
<script>
  export default {
    data: () => ({
        icons: [
            'fab fa-facebook',
            'fab fa-twitter',
            'fab fa-google-plus',
            'fab fa-linkedin',
            'fab fa-instagram'
        ],
        links: [
            'Home',
            'About Us',
            'Team',
            'Services',
            'Blog',
            'Contact Us'
        ]
    }),
    computed: {
      isHome () {
        return (this.$route.path==='/')
      },
    },
  }
</script>
