<template lang="pug">
  #app
    //- #nav
    //-   router-link(to='/') Home
    //-   |  |
    //-   router-link(to='/about') About
    router-view

</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,300;0,700;1,300;1,400&display=swap');

body,
html {
  background: transparent linear-gradient(180deg, #0f1825 0%, #0f1825 50%, #0d0d1b 100%) 0% 0% no-repeat padding-box;
  font-family: 'Roboto', sans-serif;
}
#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: transparent linear-gradient(180deg, #0f1825 0%, #0f1825 50%, #0d0d1b 100%) 0% 0% no-repeat padding-box;
  width: 70%;
  margin: auto;

  @media (max-width: 992px) {
    width: 100%;
    padding: 2rem 0.938rem;
  }
}
</style>
