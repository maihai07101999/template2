<template>
  <div class="a">
    <div class="menu">
      <div class="logo">swagger</div>
      <div class="search">
        <input type="text" value="/fe/api/doc/" class="inp" />
        <button class="btn-primary btn">Explore</button>
      </div>
    </div>
    <div class="nd">
        <h2 class="h2">System Frontend API 
            <small> <pre class="version">1.0.0</pre></small>
           
        </h2>
          <pre class="url">[ Base URL: / ]</pre>
        <small class="lin"><a href="">/fe/api/doc/</a></small>
       
    </div>
    <div class="nd1">
        <div class="cheme">
            <span class="title">Schemes</span>
            <select >
                <option value="HTTP">HTTP</option>
                <option value="HTTPS">HTTPS</option>
            </select>
        </div>
        <button class="btn1" @click="msg=!msg">Authorize </button>
    </div>
    <div class="nen" v-show="msg">
        <br>
        <p>JwtBearerToken  (apiKey)</p>
        <p>Name: Authorized</p>
        <p>In: header</p>
        <small style="float:left">Value:</small> <p v-show="!hs" style="float:left">********</p>
        <input type="text" v-show="hs" > <br> <br> 
          <button class="aut" button @click="hs=!hs" v-show="hs">Authorize</button> <button @click="hs=!hs" v-show="!hs" class="log">Log out</button> <button  @click="msg=!msg" class="clo">Close</button> 
        <hr>
         <p>JwtBearerToken  (apiKey)</p>
        <p>Name: Authorized</p>
        <p>In: header</p>
        <small style="float:left">Value:</small><p  v-show="!ha" style="float:left">********</p>
        <input type="text" v-show="ha">  <br> <br>
          <button class="aut" button @click="ha=!ha" v-show="ha">Authorize</button> <button @click="ha=!ha" v-show="!ha" class="log">Log out</button> <button  @click="msg=!msg" class="clo">Close</button> 
    </div>
  </div>
</template>
<script>

export default {
   name: "#mmm",
   data(){
       return{
           msg: false,
           hs:true,
           ha: true
       }
   }
}
</script>

<style scoped>
    #a {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 0;
  margin: 0!important;
    }
    .aut, .clo, .log{
        width: 70px;
        height: 30px;
        border: 2px solid #547f00;
        background-color: rgb(248, 218, 218);
        border-radius: 5px;
        cursor: pointer;
    }
    .nen{
        width: 40%;
        height: 50%;
        background-color: rgb(248, 218, 218);
        position: absolute;
        left: 25%;
       text-align: left;
       padding-left: 30px;
        top: 10%;
        z-index: 5;

    }
    .btn1{
       
        width: 140px;
        height: 35px;
        background-color: white;
        border: 2px solid rgb(46, 151, 46);
        border-radius: 5px;
        color: rgb(46, 151, 46);
        float: right;
       cursor: pointer;
    }
    .nd1{
       padding: 10px 15% 10px 10%;
        width: 75%;
        height: 80px;
        border-bottom: 0.5px solid rgb(201, 198, 198);
    }
    .cheme{
        float: left;
        padding-top: 10px;
        width: 150px;
        height: 100%;
        
    }
    .title{
        float: left;
        padding-left: 5px;
        font-size: 11px;
        font-weight: bold;
        
    }
    select{
        float: left;
        margin-left:3px;
        width: 70%;
        height: 40%;
    }
    .nd{
        width: 80%;
        height: 10%;
        background-color: rgb(245, 243, 241);
        padding:10px 10%;
        text-align: left;

    }
    .url{
       transform: translateY(-40px)
    }
    .lin{
        transform: translateY(-30px) !important;
        
    }
    .h2{
        position: relative;
        margin: 0px;

    }
  
    .version{
      position: relative;
     top: -45px;
    left: 250px;
    }
    .menu{
        padding: 10px 15% 10px 10%;
        width: 75%;
        height: 33px;
        background-color: #89bf04;
    }
    .logo{
        float:left;
        font-size: 22px;
        color: aliceblue;
        font-weight: bold;
    }
    .search{
        width: 70%;
        height: 90%;
         border-radius:3px;
         overflow: hidden;
         float: right;
         background-color: #547f00
    }
    .inp{
        width: 90%;
        height: 95%;
        float:left;
        border: none;
    }
    .btn{
        width: 9%;
        height: 100%;
        float: left;
        background-color: #547f00;
        border:none;
        cursor: pointer;
    }
</style>