<template>
  <div class="wrapper" @mousemove="moveCursor">
    <header class="header">
      <a href="#" class="header__logo" title="drag me">Logo Logo</a>
        <div class="burger-button" @click="showMenu">
          <div class="burger-button__lines"></div>
        </div>
      <nav class="navigation" v-bind:class="{ 'navigation--open': isActive }">
        <ul class="navigation__list">
          <li class="close-button" @click="hideMenu"></li>
          <li class="navigation__item">
            <a href="#" class="navigation__link">
              Commercial
            </a>
          </li>
          <li class="navigation__item">
            <a href="#" class="navigation__link">
              Editorial
            </a>
          </li>
          <li class="navigation__item">
            <a href="#" class="navigation__link">
              Reportage
            </a>
          </li>
          <li class="navigation__item">
            <a href="#" class="navigation__link">
              Meet Me
            </a>
          </li>
        </ul>
      </nav>
    </header>
    <div class="slider">
      <div
        class="slider__item slider__item--prev"
        :style="parallax(10, 1.1)"></div>
      <div
        class="slider__item slider__item--current"
        :style="parallax(30, 1.5)"></div>
      <div
        class="slider__item slider__item--next"
        :style="parallax(60, 2.03)"></div>
    </div>
    <div class="slider__title">
        <div class="title">Ink Lingerie</div>
        <div class="title title--current">Ink Lingerie</div>
        <div class="title">Ink Lingerie</div>
    </div>
    <footer class="footer">
      <a href="https://www.instagram.com/vitalii_kuzmichov/" class="footer__link">Inst</a>
      <div class="footer__line"></div>
      <a href="https://www.facebook.com/profile.php?id=100007685329154" class="footer__link">Fb</a>
    </footer>
    <div class="dragtip" :style="cursorPoint">Drag me</div>
  </div>
</template>

<script>
export default {
  name: 'MainPage',
  data() {
    return {
      xChild: 0,
      yChild: 0,
      isActive: false,
    };
  },
  computed: {
    cursorPoint() {
      return `top: ${this.yChild}px;
      left: ${this.xChild}px;`;
    },
  },
  methods: {
    moveCursor(e) {
      this.xChild = e.clientX;
      this.yChild = e.clientY;
    },
    parallax(speed, deg) {
      return `transform: translateX(${(this.xChild * speed) / 1000}px) translateY(${(this.yChild * speed) / 1000}px) rotate(${deg}deg)`;
    },
    showMenu() {
      this.isActive = true;
    },
    hideMenu() {
      this.isActive = false;
    },
  },
};
</script>

<style lang="scss">

.wrapper {
  width: 100vw;
  height: 100vh;
  position: relative;
  background-color: #e5e5e5;
  padding: 3.33vw 5.56vh;
  background-image: url(../assets/Vector.svg);
  background-repeat: no-repeat;
  background-position: center;
  background-size: 45%;
  overflow: hidden;
}

.header {
  display: flex;
  justify-content: space-between;

  &__logo {
    font-family: GT America Expanded Bold, Arial, sans-serif;
  }
}

.navigation {
  position: absolute;
  background-color: #580300;
  font-size: 30px;
  width: 100vw;
  top: 0;
  right: 0;
  z-index: 999;
  transform: translateX(100%);
  transition: transform .3s;

  &__list {
    margin-top: 50px;
  }

  &__item {
    margin: 50px 0;
  }

  &__link {
    letter-spacing: 2%;
    transition: color .3s;
    &:hover {
      color: #fff;
    }
  }
}

.navigation--open {
  transition: transform .3s;
  transform: translateX(0);
}

.close-button {
  display: block;
  height: 30px;
  z-index: 1000;
  background-image: url(../assets/cross.svg);
  background-repeat: no-repeat;
  background-position: 90% 0;
}

.dragtip {
  display: block;
  position: absolute;
  font-size: 8px;
  text-transform: uppercase;
  transform: translate(50%, -45%);
  opacity: 0;
  transition: opacity .6s;
}

.burger-button {
  position: relative;
  width: 140px;
  height: 40px;
  z-index: 900;

  &__lines {
    position: absolute;
    width: 20px;
    height: 10px;
    top: 10px;
    right: 0;
    border-top: 1px solid;
    border-bottom: 1px solid;
  }
}

.slider {
  width: 100%;
  height: 81.5%;
  position: relative;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  &__title:hover ~ .dragtip {
    transition: opacity .6s;
    opacity: 1;
  }

  &__item {
    position: absolute;
    background-size: cover;
    background-position: center;
  }

  &__item--prev {
    display: none;
    width: 16.5vw;
    height: 38vh;
    top: 7vw;
    left: 15.5vw;
    background-image: url(../assets/image2.png)
  }

  &__item--current {
    width: 73vw;
    height: 81vh;
    margin: 0 auto;
    left: 0;
    right: 0;
    background-position-y: top;
    background-image: url(../assets/image1.png);
  }

  &__item--next {
    display: none;
    width: 24vw;
    height: 27.6vh;
    top: 24vw;
    right: 12.94vw;
    background-image: url(../assets/image3.png)
  }

  &__title {
    position: absolute;
    width: 145%;
    height: 28vw;
    top: 50%;
    left: -20%;
    transform: translateY(-50%);
    display: flex;
    justify-content: space-between;
  }
}

.title {
  margin-top: 10.41vw;
  font-family: Schnyder Cond XL Demi, Arial, sans-serif;
  font-size: 44px;
  text-transform: uppercase;
  color: #e5e5e5;
  text-shadow: 0px 0px 2px #580300;
  opacity: .7;

  &:first-of-type {
    transform: rotate(-1.5deg)
  }

  &:last-of-type {
    transform: rotate(1.5deg)
  }

  &--current {
    text-shadow: none;
    color: #580300;
  }
}

.footer {
  position: absolute;
  display: flex;
  justify-content: space-between;
  align-content: center;
  width: 112px;
  height: 20px;
  left: 3.33vw;
  bottom: 3.33vw;

  &__link {
    font-size: 11px;
    line-height: 20px;
    transition: color .3s;

    &:hover {
      color: #580300;
    }
  }

  &__line {
  width: 56px;
  margin-top: 9px;
  border-top: 0.05vw solid;
  opacity: 0.24;
}
}

@media screen and (min-width: 768px) {

.navigation {
  position: relative;
  background-color: initial;
  font-size: 12px;
  width: initial;
  transform: none;

  &__list {
    margin: 0;
    text-align: right;
  }

  &__item {
    margin: 10px 0;

    &:first-of-type {
      margin-top: 0;
    }
  }

  &__link {
    &:hover {
      color: #580300;
    }
  }
}

.slider__item--prev {
  display: block;
}

.slider__item--current {
  width: 33vw;
}

.slider__item--next {
  display: block;
}

.navigation--open {
  transform: none;
}

.close-button {
  display: none;
}

.burger-button {
  display: none;
}

.title {
  font-size: 8.48vw;
}

}
</style>
