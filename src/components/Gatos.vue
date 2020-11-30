<template>
  <div>
    <header class="header">
      <h1>
        <span>C</span>
        <span>A</span>
        <span>T</span>
        <span>S</span>
      </h1>
    </header>
    <main class="main text-center">
      <form @submit.prevent="buscar">
        <div class="main__div">
          <span :class="''">Titulo: </span>
          <input class="form-control" type="text" placeholder="">
        </div>
        <div class="main__div">
          <span>Color:</span>
          <select class="form-control">
            <option>Azul</option>
            <option>Verde</option>
            <option>Rojo</option>
            <option>Negro</option>
          </select>
        </div>
        <div class="main__div">
          <span>Filtro:</span>
          <select class="form-control">
            <option>Blur</option>
            <option>Mono</option>
            <option>Sepia</option>
            <option>Negavite</option>
            <option>Paint</option>
            <option>Picel</option>
          </select>
        </div>
        <div class="main__div">
          <span>Tamaño:</span>
          <input class="form-control" type="text" placeholder="">
        </div>
        <div>
          <button class="btn btn-dark p-3 m-2" type="submit">Obtener Michi</button>
        </div>
      </form>
      <div>
        <img :src="getInfo" alt="">
      </div>
    </main>

  </div>
</template>

<script>
export default {
  name: 'Gatos',
  data() {
    return {
      michi: [],
    }
  },
  // mounted() {
  //   fetch("https://cataas.com/cat/gif/says/holi?filter=sepia&color=orange&size=40&type=or")
  //   .then((resp) => resp.json())
  //   .then((result) =>{
  //     this.michi = result;
  //   })
  // },
    methods: {
    buscar(){
      fetch("https://cataas.com/cat/gif/says/holi?filter=sepia&color=orange&size=40&type=or")
      .then((resp) => resp.json())
      .then((result) =>{
        this.michi = result;
      })
      // .catch((error) => {
      //   console.log(error)
      //   alert("El nombre o número no es correcto");
      // })
    }
  },
  computed: {
    getInfo() {
      if (this.michi) {
        return this.michi;
      }else {
        return '';
      }
    }
  },
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  width: 100%;
  height: 100px;
  display: flex;
  align-content: center;
  justify-content: center;
}
.header h1 {
  margin-top: 20px;
}
.header h1 span:nth-child(1){
    animation-delay: 0s;
}
.header h1 span:nth-child(2){
    animation-delay: 0.5s;
}
.header h1 span:nth-child(3){
    animation-delay: 1s;
}
.header h1 span:nth-child(4){
    animation-delay: 1.5s;
}
@keyframes animate{
    0%, 100% {
        color: #fff;
        filter: blur(0px);
        text-shadow: 0 0 10px #eeff00, 0 0 20px #eeff00, 0 0 30px #eeff00, 0 0 40px #eeff00,0 0 50px #eeff00;
    }
    30%, 70% {
        color: #7c7c7c;
        filter: blur(0%);
        text-shadow:  none;
    }
}
.header h1 span {
    display: table-cell;
    margin: 0;
    padding: 0;
    animation: animate 2s linear infinite;
}
.main {
  width: 100%;
  height: auto;
  background: rgb(251, 255, 0);
  border: 3px solid rgb(0, 0, 0);
}
.main__div {
  display: flex;
  padding: 20px;
}
.main__div span {
  margin-right: 20px;
}
.section__div {
  height: 500px;
}
</style>
