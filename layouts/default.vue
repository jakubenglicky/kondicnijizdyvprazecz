<template>
  <div>
    <Header />
    <Nuxt />      
    <!--<CookiesPopUp />-->
    <Footer />
  </div>
</template>

<script>
import Header from '~/components/Header';
import Footer from '~/components/Footer';

export default {
  methods: {
    getCookie(name) {
      const value = `; ${document.cookie}`
      const parts = value.split(`; ${name}=`)
      return parts.length !== 2 ?
      undefined :
      parts.pop().split(';').shift()
    },
    activateGA() {
      this.$ga.enable(); // Activate module
      this.$ga.page(this.$route.path); // Track current route
    },
    consentGranted(analytisc, ad) {
        gtag('consent', 'update', {
            'ad_storage': ad,
            'analytics_storage': analytisc
        });
    },
  }/*,
  mounted() {
    this.$ga.disable();

    let cookieConsent = this.getCookie("cookieconsent_status_new")
    if (cookieConsent && cookieConsent !== 'none') {
      if (cookieConsent === 'all') {
        this.consentGranted('granted', 'granted')
      }
      if (cookieConsent === 'analytic') {
        this.consentGranted('granted', 'denied')
      }
      if (cookieConsent === 'marketing') {
        this.consentGranted('denied', 'granted')
      }
    }

    onAnalyticsReady().then(() => {
      const cokConsent = this.getCookie("cookieconsent_status_new") // Your logic for consent
      if (cokConsent && cokConsent !== 'none') {
        this.activateGA()
      }
    });
  }*/
}
</script>
