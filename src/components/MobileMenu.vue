<template>
  <div class="container">
    <div class="menu">
    <div class="brand">
      <router-link to="/"
      >
        <img class="mainlogo" src="../assets/logo/Logo-no-background.png" alt=""/>

    </router-link>
          
    </div>

      <div>
        <div
          class="hamburger"
          :class="{ open: isOpen }"
          id="hamburger-6"
          v-on:click="isOpen = !isOpen"
        >
          <span class="line"></span>
          <span class="line"></span>
          <span class="line"></span>
        </div>
      </div>
    </div>

    <div class="list" :class="{ active: isOpen }">
      <div class="item" v-on:click="isOpen = false">
        <router-link to="/Services">SERVICES</router-link>
      </div>
      <div class="item" v-on:click="isOpen = false">
        <router-link to="/about-us">ABOUT US</router-link>
      </div>
      <div class="item" v-on:click="isOpen = false">
        <router-link :to="{ path:'/', hash:'#work'}">WORK</router-link>
      </div>
      <div class="item" v-on:click="isOpen = false">
        <router-link :to="{ path:'/', hash:'#testimonial'}">TESTIMONIAL</router-link>
      </div>
      <div class="item" v-on:click="isOpen = false">
        <router-link :to="{ path:'/', hash:'#contact'}">CONTACT US</router-link>
      </div>
      <div class="item" v-on:click="open">
       <div class="phone-number">805-487-1477</div>
      </div>      
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
      showBox: false
    };
  },

  methods: {
    open() {
      this.isOpen = false
      this.$emit("showQuote", true);
    }
  }
};
</script>
<style scoped>
.open span {
  -webkit-transition: all 0.3s ease-in-out;
  -o-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
  -webkit-transition-delay: 0.6s;
  -o-transition-delay: 0.6s;
  transition-delay: 0.6s;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
  transform: rotate(45deg);
}
#hamburger-6.open .line:nth-child(2) {
  width: 0px;
}

#hamburger-6.open .line:nth-child(1),
#hamburger-6.open .line:nth-child(3) {
  -webkit-transition-delay: 0.3s;
  -o-transition-delay: 0.3s;
  transition-delay: 0.3s;
}

#hamburger-6.open .line:nth-child(1) {
  -webkit-transform: translateY(13px);
  -ms-transform: translateY(13px);
  -o-transform: translateY(13px);
  transform: translateY(13px) rotate(135deg);
}

#hamburger-6.open .line:nth-child(3) {
  -webkit-transform: translateY(-13px) rotate(90deg);
  -ms-transform: translateY(-13px) rotate(90deg);
  -o-transform: translateY(-13px) rotate(90deg);
  transform: translateY(-13px) rotate(45deg);
}
.hamburger {
  margin-top: 1em;
}
.hamburger .line {
  width: 50px;
  height: 5px;
  background-color: #ecf0f1;
  display: block;
  margin: 8px 2em;
  -webkit-transition: all 0.3s ease-in-out;
  -o-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
}
.menu {
  display: flex;
  justify-content: space-between;
  z-index: 1;
  color: white;
  background-color: orangered;
}
.list {
  height: 0;
  position: relative;
  top: -24em;
  z-index: -2;
  transition: ease 0.5s;
  width: 100%;
  text-align: center;
}
.list .item {
  background-color: white;
}
.phone-number {
  background-color: orangered !important;
  color: white;
  font-size: 1em;
  border-radius: 15px;
  padding: 10px;
  cursor: pointer;
  margin: 0 auto;
}
.list.active {
  top: 0;
}

@media screen and (min-width: 1314px) {
  .container {
    display: none;
  }
}

.hamburger {
  cursor: pointer;
}
.container {
  position: fixed;
  width: 100%;
  z-index: 99;
}
.mainlogo {
  height: 55px;
  margin-top: 2px;
  cursor: pointer;
}

</style>
