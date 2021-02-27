<template>
  <body>
      <header id="top-header">
        <div class="flex">
          <h1 class="header-logo">estra inc.</h1>
          <nav class="header-nav">
            <ul>
              <li><a href="#">home</a></li>
              <li><a href="#">about</a></li>
              <li><a href="#">service</a></li>
              <li><a href="#">works</a></li>
              <li><a href="#">price</a></li>
              <li><a href="#">contact</a></li>
            </ul>
          </nav>
        </div>
      </header>

    <div id="hamburger" @click="hamburger()" :class="{'active':isClass}">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <nav class="hiden-nav" :class="{'open':isClass}">
      <ul class="hiden-nav-content">
        <li><a href="#">home</a></li>
        <li><a href="#">about</a></li>
        <li><a href="#">service</a></li>
        <li><a href="#">works</a></li>
        <li><a href="#">price</a></li>
        <li><a href="#">contact</a></li>
      </ul>
    </nav>
  </body>
</template>

<script>
export default {
  data() {
    return {
      isClass: false
    };
  },
  methods: {
    hamburger() {
      this.isClass = !this.isClass;
    }
  }
}
</script>

<style scoped>

/*------------------------*/
/*         header         */
/*------------------------*/


#hamburger {
  display: none;
}

#top-header {
  height: 70px;
  line-height: 70px;
  background: rgba(0, 0, 0, 1);
}

.header-logo {
  font-size: 20px;
  font-weight: bold;
  margin-left: 35px;
  color: #fff;
  line-height: 70px;
}

.header-nav li {
  display: inline-block;
  margin-right: 35px;
  font-size: 16px;
}

.header-nav a {
  color: #fff;
}

.body {
  height: 100%;
}

.hiden-nav {
  display: block;
  width: 100%;
  height: 100%;
  text-align: center;
  position: fixed;
  top: 0;
  left: -100%;
  transition: 0.2s;
  background: white;
  z-index: 100;
}


@media screen and (max-width: 768px) {
  .header-nav {
    display: none;
  }

  #hamburger {
    width: 40px;
    height: 40px;
    position: absolute;
    cursor: pointer;
    z-index: 200;
    top: 15px;
    right: 20px;
    transition: 0.4s;
    display: block;
  }
  #hamburger span {
    display: block;
    width: 35px;
    height: 2px;
    background-color: #fff;
    transition: 0.8s;
  }
  #hamburger span:nth-of-type(1) {
    position: absolute;
    top: 10px;
    left: 2px;
  }
  #hamburger span:nth-of-type(2) {
    position: absolute;
    top: 20px;
    left: 2px;
  }
  #hamburger span:nth-of-type(3) {
    position: absolute;
    top: 30px;
    left: 2px;
  }

  #hamburger.active span:nth-of-type(1) {
  top: 20px;
  transform: rotate(45deg);
  background-color: black;
}

  #hamburger.active span:nth-of-type(2) {
  opacity: 0;
}
  #hamburger.active span:nth-of-type(3) {
  top: 20px;
  transform: rotate(-45deg);
  background-color: black;
}


.hiden-nav-content{
  margin: 4rem 0;
  font-size: 2rem;
  font-weight: bold;
} 

.hiden-nav-content li {
  margin: 2rem;
}

.hiden-nav.open {
  left: 0;
}
}

</style>