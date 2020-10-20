<template>
  <div>

    <div class="retangulo"></div>
    <img src="../assets/logo.png" class="logo" fluid alt="Responsive image" />
    <div class="retangulo_arredondado"></div>

    <div class="bloco1">
      <h2>VX Comunicação</h2>
      <h3>WebSite</h3>
      <b-avatar rounded="sm" class="foto"></b-avatar>
    </div>
  
    <b-navbar toggleable="lg" type="dark" class="navbar">
      <b-navbar-brand href="#" class="nav-item barra">TimeLine</b-navbar-brand>
      <b-navbar-brand href="#" class="nav-item">About</b-navbar-brand>
      <b-navbar-brand href="#" class="nav-item">Welcome</b-navbar-brand>
      <b-navbar-brand href="#" class="nav-item">VX</b-navbar-brand>
    </b-navbar>

    <div class="about-header">
      <p>Sobre</p>
    </div>
    <div class="about-body">
      <p>Lorem Ipsum is simply dummy text of the printing and 
        typesetting industry. Lorem Ipsum has been the 
        industry's standard dummy text ever since the 1500s, 
        when an unknown printer took a galley of type and 
        scrambled it to make a type specimen book. It has 
        survived not only five centuries, but also the leap into 
        electronic typesetting, remaining essentially unchanged. 
        It was popularised in the 1960s.<br/><br/>
        Site: https://vxcomunicacao.com.br<br />
        Email: contato@vxcomunicacao.com.br
      </p>
    </div>

    <div class="TimeLine">
      <p>O que você está pensando ?</p>
      <b-form-textarea
        id="textarea"
        rows="3"
        max-rows="6"
        v-model="message"
      ></b-form-textarea>
      <b-button class="button" v-on:click="addPublish">Enviar</b-button>
    </div>

    <div class="publish">
      <b-avatar rounded="sm" src="" size="4rem" class="avatar"></b-avatar>
      <p class="name">Natália</p>
      <p class="type">Atualizou a foto</p>
      <p class="time">3 minutos atrás</p>
      <b-img src="https://picsum.photos/1024/400/?image=41" fluid alt="Responsive image"></b-img>
      <b-button variant="link"  class="curtir" v-on:click="addQtd">Curtir[{{ contador }}]</b-button>
      <b-button variant="link" class="comentar">Comentar</b-button>
      <b-button variant="link" class="compartilhar">Compartilhar</b-button>
   </div>

    <div class="publish1">
      <b-avatar rounded="sm" src="" size="4rem" class="avatar"></b-avatar>
      <p class="name">Natália</p>
      <p class="type">Escreveu uma publicação</p>
      <p class="time2">8 minutos atrás</p>
      <p class="message">
        Lorem Ipsum is simply dummy text of the printing and 
        typesetting industry. Lorem Ipsum has been the 
        industry's standard dummy text ever since the 1500s, 
        when an unknown printer took a galley of type and 
        scrambled it to make a type specimen book. It has 
        survived not only five centuries, but also the leap into 
        electronic typesetting, remaining essentially unchanged. 
        It was popularised in the 1960s.
      </p>
      <b-img src="https://picsum.photos/1024/400/?image=41" fluid alt="Responsive image"></b-img>
      <b-button variant="link" class="curtir" v-on:click="addQtd">Curtir[{{ contador }}]</b-button>
      <b-button variant="link" class="comentar">Comentar</b-button>
      <b-button variant="link" class="compartilhar">Compartilhar</b-button>
    </div>

    <div class="publish2">
      <b-avatar rounded="sm" src="" size="4rem" class="avatar"></b-avatar>
      <p class="name">Natália</p>
      <p class="type2">Patrocínio</p>
      <b-img src="https://picsum.photos/1024/400/?image=41" fluid alt="Responsive image"></b-img>
      <b-button variant="link"  class="curtir" v-on:click="addQtd">Curtir[{{ contador }}]</b-button>
      <b-button variant="link" class="comentar">Comentar</b-button>
      <b-button variant="link" class="compartilhar">Compartilhar</b-button>
   </div>

    <div class="publish3" >
      <b-avatar rounded="sm" src="" size="4rem" class="avatar"></b-avatar>
      <p class="name">Natália</p>
      <p class="type">Atualizou a foto</p>
      <p class="time2">3 minutos atrás</p>
      <LazyYoutubeVideo class="video" src="https://www.youtube.com/watch?v=Hy5CDC-yPx8" />
      <b-button variant="link" class="curtir" v-on:click="addQtd">Curtir[{{ contador }}]</b-button>
      <b-button variant="link" class="comentar">Comentar</b-button>
      <b-button variant="link" class="compartilhar">Compartilhar</b-button>
    </div>

  </div>
</template>

<script>
import LazyYoutubeVideo from 'vue-lazy-youtube-video';
export default {
  name: 'YourAwesomeComponent',
  components: {
    LazyYoutubeVideo,
  },
  data() {
    return {
      publish: [],
      name: 'Natália',
      type: '',
      message: '',
      contador: 0
     }
  },
  methods: {
    addPublish() {
      if (this.message.trim() === '') {
        return;
      }

      this.publish.push({
        name: this.name,
        message: this.message
      });

      this.message = '';
    },

    addQtd() {
      this.contador += 1;
    },

    select() {
      
    }
  }
}
</script>

<style scoped>
  .logo {
    position: absolute;
    left: 20%;
    top: 16px;
    width: 45px;
    height: 30px;
    z-index: 9;
  }
  .retangulo {
    position: absolute;
    width: 100%;
    height: 60px;
    z-index: 5;
    background-color: #404040;
  }
  .retangulo_arredondado {
    border-width: 1px;
    border-radius: 5px;
    position: absolute;
    left: 25%;
    top: 11px;
    width: 40%;
    height: 37px;
    z-index: 6;
    background-color: #ffffff;
  }
  .bloco1 {
    background-color: rgb(0, 175, 184);
    position: absolute;
    left: 19%;
    top: 64px;
    width: 65%;
    height: 350px;
    z-index: 13;  
  }
  h2 {
    font-family: 'Myriad Pro', sans-serif;
    font-size: 25px;
    color: #ffff;
    margin-top: 275px;
    margin-left: 150px;
  }
  h3 {
    font-family: 'Roboto', sans-serif;
    font-size: 20px;
    color: #ffff;
    margin-left: 150px;
  }
  .navbar {
    left: 19%;
    top: 414px;
    width: 65%;
    align-content: center;
    background-color:  #404040;
    font-family: 'Myriad Pro';
    padding: 15px 130px 4px;
  }
  .navbar .nav-item {
    margin: 0 20px;
  }
  /* .barra {
    background-color: rgb(0, 175, 184);
    left: 140px;
    top: 10px;
    width: 132px;
    height: 7px;
    z-index: 11;
  } */
  .foto {
    position: absolute;
    left: 1%;
    top: 75%;
    width: 15%;
    height: 135px;
    z-index: 13;
  }
  .about-header {
    border-radius: 5px;
    background-color: rgb(199, 199, 199);
    position: absolute;
    left: 19%;
    top: 480px;
    width: 25%;
    height: auto;
    z-index: 20;
  }
  .about-header p {
    font-family: 'Roboto', sans-serif;
    margin-top: revert;
    margin-left: 10px;
  }
  .about-body {
    border-style: solid;
    border-width: 1px;
    border-color: rgb(192, 192, 192);
    border-radius: 5px;
    background-color: rgb(255, 255, 255);
    position: absolute;
    left: 19%;
    top: 532px;
    width: 25%;
    height: auto;
    z-index: 25;
  }
  .about-body p {
    font-family: 'Roboto', sans-serif;
    text-align: justify;
    padding: 10px 10px 10px 10px;
  }
  .TimeLine {
    border-style: solid;
    border-width: 1px; 
    border-color: rgb(192, 192, 192);
    border-radius: 5px;
    background-color: rgb(255, 255, 255);
    position: absolute;
    left: 45%;
    top: 480px;
    width: 39%;
    height: auto;
    z-index: 67;
  }
  .TimeLine p {
    font-family: 'Roboto', sans-serif;
    font-weight: 500;
    color: #00afb8;
    padding: 10px 10px 10px 10px;
  }
  .TimeLine .textarea {
    border-radius: 5px;
    border: 1px solid #c0c0c0;
    background-color: #e8e8e8;
    margin: -20px 0px 0px 10px;
    padding: 35px 250px 30px 10px;
  }
  .TimeLine .button {
    border-color:#00afb8;
    background:linear-gradient(to bottom, #00afb8 5%, #00afb8 100%);
    box-shadow:inset 0px 1px 0px 0px #d7ecfd;
    color:#fff;
    text-shadow:0px 1px 0px #00afb8; 
    margin: 10px 0px 10px 10px;
    border-radius: 5px;
  }
  .publish {
    border-style: solid;
    border-width: 1px;
    border-color: rgb(192, 192, 192);
    border-radius: 5px;
    background-color: rgb(255, 255, 255);
    position: absolute;
    left: 45%;
    top: 705px;
    width: 39%;
    height: auto;
    z-index: 57;
  }
  .publish1 {
    border-style: solid;
    border-width: 1px;
    border-color: rgb(192, 192, 192);
    border-radius: 5px;
    background-color: rgb(255, 255, 255);
    position: absolute;
    left: 45%;
    top: 1090px;
    width: 39%;
    height: auto;
    z-index: 57;
  }
  .publish2 {
    border-style: solid;
    border-width: 1px;
    border-color: rgb(192, 192, 192);
    border-radius: 5px;
    background-color:#404040;
    position: absolute;
    left: 45%;
    top: 1604px;
    width: 39%;
    height: auto;
    z-index: 57;
  }
  .publish3 {
    border-style: solid;
    border-width: 1px;
    border-color: rgb(192, 192, 192);
    border-radius: 5px;
    background-color: rgb(255, 255, 255);
    position: absolute;
    left: 45%;
    top: 1990px;
    width: 39%;
    height: auto;
    z-index: 57;
  }
  .avatar {
    margin: 10px 0px 0px 10px;
  }
  .name {
    font-family: 'Roboto', sans-serif;
    font-weight: 500;
    font-size: 17px;
    color: #00afb8;
    margin: -65px 0px 0px 95px;
  }
  .type {
    font-family: 'Roboto', sans-serif;
    font-weight: 500;
    font-size: 12px;
    color: #a7a7a7;
    margin: -20px 0px 0px 155px
  }
  .type2 { 
    font-family: 'Roboto', sans-serif;
    font-weight: 500;
    font-size: 12px;
    color: #a7a7a7;
    margin-left: 95px;
  }
  .message {
    font-family: 'Roboto', sans-serif;
    font-weight: 500;
    font-size: 15px;
    color: #a7a7a7;
    margin: 55px 0px 0px 10px;
    text-align: justify;
    padding: 0px 10px 10px 0px;
  }
  button {
    margin-top: 15px;
  }
  .publish img, .publish2 img {
    margin-top: 50px;
  }
  .select {
    background-color: rgb(0, 175, 184);
    position: absolute;
    left: 1026px;
    top: 877px;
    width: 132px;
    height: 7px;
    z-index: 11;
  }
  .video {
    margin-top: 50px;
  }
  .curtir, .curtir:hover {
    color: rgb(0, 175, 184);
    text-decoration:none
  }
  .comentar, .compartilhar, .comentar:hover, .compartilhar:hover {
    color:#a7a7a7;
    text-decoration:none
  }
  .time {
    margin-top: 1px;
    margin-left: 94px;
    color: #a7a7a7;
    font-size: 11px;
  }
  .time2 {
    margin-top: 1px;
    margin-left: 94px;
    color:rgb(0, 175, 184);
    font-size: 11px;
  }
</style>