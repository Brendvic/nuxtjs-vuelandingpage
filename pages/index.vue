<template>
    <NavbarHeader />
    <TaglineSection />
    <CardSection />
    <FindSection />
    <SocialProof />
    <FaqSection />
    <ContactSection />
    <FooterSection />
</template>
  
<script>
  import NavbarHeader from '~/components/NavbarHeader.vue'
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
      NavbarHeader,
      TaglineSection,
      CardSection,
      FindSection,
      SocialProof,
      FaqSection,
      ContactSection,
      FooterSection,
    },
    methods: {
    redirectToLogin() {
      this.$router.push('/login');
      console.log('Email:', this.email, 'Password:', this.password);
    },
    redirectToSignup() {
      this.$router.push('/signup');
      console.log('Email:', this.email, 'Password:', this.password);
    }
  },
};
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
  