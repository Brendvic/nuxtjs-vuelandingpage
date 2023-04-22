<template>
    <NavbarHeader1 />
    <TaglineSection />
    <CardSection />
    <FindSection />
    <SocialProof />
    <FaqSection />
    <ContactSection />
    <FooterSection />
</template>
  
<script>
  import NavbarHeader1 from '~/components/NavbarHeader1.vue'
  import TaglineSection from '~/components/TaglineSection.vue'
  import CardSection from '~/components/CardSection.vue'
  import FindSection from '~/components/FindSection.vue'
  import SocialProof from '~/components/SocialProof.vue'
  import FaqSection from '~/components/FaqSection.vue'
  import ContactSection from '~/components/ContactSection.vue'
  import FooterSection from '~/components/FooterSection.vue'

  export default {
    name: 'app',
    components: {
      NavbarHeader1,
      TaglineSection,
      CardSection,
      FindSection,
      SocialProof,
      FaqSection,
      ContactSection,
      FooterSection,
    },
    methods: {
      redirectToLogout() {
      this.$router.push('/');
      console.log('Email:', this.email, 'Password:', this.password);
      Cookies.remove('auth_token') 
      this.authToken = ''
  }
 }
}  
</script>
  
  <style>
  #app {
    height: 100vh;
    background-image: #FFFFFF;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  
  }
  </style>
  