<template>
  <div id="nav">
    <router-link to="/">Home</router-link> 
    <router-link to="/about">About</router-link>
      <img alt="Human Logo" src="./assets/human.jpg" class="navlogo"/>
    <router-link to="/about">Gallery</router-link> 
    <router-link to="/about">Contact</router-link>
  </div>
  <router-view/>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Abel&display=swap');
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav{
  position: fixed;
  bottom: 5%;
  width: 100%;
  overflow:hidden;
  height:100px;
  text-align:center;
  justify-content: center;
  display: flex;
  left:2%;
}
#nav a {
  margin: 5vw;
  font-family: 'Abel', sans-serif;
  color:#fff !important;
  text-decoration: none;
  letter-spacing: 5px;
  font-size: 18px;
  text-transform: uppercase;
  font-weight: 100;
}
#nav .navlogo{
  margin:0 auto;
  height: 60px;
  margin:10px;
  margin-top: 30px;
  
  width:60px;
  border-radius: 50%;
}
body {
  background: linear-gradient(90deg, #bd0f4d 50%, #cb2964 50%);


}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
