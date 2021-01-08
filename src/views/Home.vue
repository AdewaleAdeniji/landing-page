<template>
  <div class="appname">
    
      {{name}}</div>
  <div class="home">
    <img src="../assets/woman3.png" alt="woman picture" class="imghome"/>

  </div>
  <div id="applinks">
    <ul>
      <li>
         <a :href="instagramlink">
          <i class="fab fa-instagram"></i>
          </a>
      </li>
       <li>
         <a :href="twitterlink">
          <i class="fab fa-twitter-square"></i>
          </a>
      </li>
       <li>
         <a :href="snapchatlink">
          <i class="fab fa-snapchat-square"></i>
          </a>
      </li>
       <li>
         <a :href="emailaddress">
          <i class="fa fa-envelope-square"></i>
          </a>
      </li>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src


export default {
  name: 'Home',
  data(){
      return {
        name:'',
        loading:true, 
        instagramlink:'',
        twitterlink:'',
        snapchatlink:'',
        emailaddress:'',
      }
  },
  created(){
    fetch('https://hirng-x2021.glitch.me/api')
    .then(response=>response.json())
    .then((data)=>{
       let name = data.name;
       let socialmedia = data.social_media;
        this.loading = false;
        this.name = name;
        this.instagramlink = 'https://www.instagram.com/'+socialmedia.instagram;
        this.twitterlink = 'https://www.twitter.com/'+socialmedia.twitter;
        this.snapchatlink = 'https://www.snapchat.com/'+socialmedia.snapchat;
        this.emailaddress = 'mailto:'+socialmedia.email;
    })
    .catch((err)=>{
      console.log(err);
     // window.location.reload();
    })
  }
}
</script>
<style scoped>
#applinks ul {
  list-style: none;

}
#applinks {
  position: fixed;
  right:3%;
  top:20%;
}
#applinks ul li {
  margin-top:5vh;
}
#applinks a {
  color:#fff;
  font-size: 30px;
}
.appname {
    color: #fff;
    font-size: 2em;
    font-family: 'Abel';
    font-weight: 100;
    letter-spacing: 5px;
    margin-top: 5vh;
}
  .home  {
    position:fixed;
    top:20%;
    width: 40vw;
    height: 50vh;
    left: 29vw;
    
    background-image:  linear-gradient(160deg, #c5235f,#ad164d);
    background-position: center;
    background-position: center;
    background-size:cover;
    background-repeat: no-repeat;
    justify-content: center;
    object-position: center;
    align-items: center;
  }
  .home img {
      width: 100%;
      height: 100%;
  }
</style>
