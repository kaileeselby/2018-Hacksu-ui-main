<template>
  <div id="app">
    <header>
    <ul id="banner">
      <a href="/" class="bannerItem">
        Home
      </a>
      <a href="https://khe.io" class="bannerItem" target="_blank">
        Kent Hack Enough
      </a>
      <a href="#" class="bannerItem">
        Contact (Not implemented)
      </a>
      <a href="#" class="bannerItem">
        Constitution (Not implemented)
      </a>
      <a href="FAQ" class="bannerItem">
        FAQ
      </a>
      <a @click="loginShown = !loginShown" class="bannerItem">
        <div class="subMenu" v-if="loginShown">
          <a @click="loginModule = !loginModule">Login </a>
          <a>Register</a>
        </div>
          
        Login/Register
      </a>
    </ul>
    </header>
    
    <div id="loginStuff" v-if="loginModule">
      <div id="dimmer"> 
      </div> 
        <loginModule>
        </loginModule> 
    </div>
    
    <router-view/>
  </div>
</template>

<script>
import loginModule from './components/Login';
export default {
  name: 'app',
  components: {
    loginModule
  },
  data() {
    return {
      loginShown: false,
      loginModule: false,
    }
  }
};
</script>

<style>
  
header {
  display: flex;
  justify-content: flex-end;

  width: 100%;
  max-width: 1440px;
}

header li {
  display: inline-block;
  padding: 20px 20px;

  font-family: 'Abel', sans-serif;
}
  
#banner {
  width: 100%;
  position: fixed;
  background: #041017;
  z-index: 1000;
  display: flex;
  justify-content: flex-end;
  margin-top: 0px;
  top: 0px;
  margin-right: 0px;
  right: 0px;

}
  #loginModule{
    top: 120px;
    height: 400px;
    width: 500px;
    background-color: #4683FF;
    position: absolute;
    display: static;
    left: 0;
    right: 0;
    z-index: 40;
    margin: auto;
    
  }
.bannerItem {
  color: white;
  transition-duration: .3s;
  height: 100%;
  display: inline-block;
  padding: 20px 20px;
  cursor: pointer;

}
.bannerItem:hover {
  background: #4683FF;

}
  
  .subMenu {
    background: white;
    color: black;
    text-decoration: none;
    position: absolute;
    margin-top: 40px;
    margin-left: -20px;
    box-shadow: 0px 0px 20px rgba(0,0,0,.3);
    animation: slideOut .3s linear;
    overflow: hidden;
  }
  
  .subMenu a {
    display: block;
    padding: 10px;
    border-bottom: solid 1px black;
    min-width: 100px;
    transition-duration: .3s;
  }
  .subMenu a:hover {
    background: lightgray;
  }
  
  @keyframes slideOut {
    from {
      max-height: 0px;
    }
    to {
      max-height: 400px;
    }
  }
  
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}
  #dimmer {
    position: absolute;
    width: 1000%;
    height: 100%;
    opacity: 0.5;
    background-color:#000;
    z-index: 20;
    left: 0;
  }
  
</style>
