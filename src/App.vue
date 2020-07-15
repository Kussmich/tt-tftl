<template>
  <div id="app">
    <MainPage />
  </div>
</template>

<script>
import MainPage from './components/MainPage.vue';

export default {
  name: 'App',
  components: {
    MainPage,
  },
};
</script>

<style lang="scss">

@font-face {
  font-family: 'TT Travels Light';
  src: url('./assets/fonts/TTTravels-Light.eot');
  src: url('./assets/fonts/TTTravels-Light.eot?#iefix') format('embedded-opentype'),
  url('./assets/fonts/TTTravels-Light.woff') format('woff'),
  url('./assets/fonts/TTTravels-Light.ttf') format('truetype');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: 'Schnyder Cond XL Demi';
  src: url('./assets/fonts/Schnyder_X_Cond_XL_Demi.otf');
  font-weight: normal;
  font-style: normal;
}

@font-face {
  font-family: "GT America Expanded Bold";
  src: url("//db.onlinewebfonts.com/t/22b4c73e6141de7c9937f42cb58bdb4b.eot");
  src: url("//db.onlinewebfonts.com/t/22b4c73e6141de7c9937f42cb58bdb4b.eot?#iefix")
  format("embedded-opentype"),
  url("//db.onlinewebfonts.com/t/22b4c73e6141de7c9937f42cb58bdb4b.woff2") format("woff2"),
  url("//db.onlinewebfonts.com/t/22b4c73e6141de7c9937f42cb58bdb4b.woff") format("woff"),
  url("//db.onlinewebfonts.com/t/22b4c73e6141de7c9937f42cb58bdb4b.ttf") format("truetype"),
  url("//db.onlinewebfonts.com/t/22b4c73e6141de7c9937f42cb58bdb4b.svg#GT America Expanded Bold")
  format("svg");
}

* {
  box-sizing: border-box;
}

html {
  cursor: url(./assets/cursor.svg), default;
}

body {
  margin: 0;
}

ul {
  list-style: none;
  padding: 0;
}

a {
  text-decoration: none;
  color: #000;
}

#app {
  font-family: TT Travels Light, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000;
}

.cursor {
  width: 17px;
  height: 17px;
  border: 1px solid;
  border-radius: 50%;
  opacity: 40%;
}

</style>
