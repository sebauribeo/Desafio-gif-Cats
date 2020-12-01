<template>
  <div>
    <div>

      <div class="header">
        <h1>
          <span>C</span>
          <span>A</span>
          <span>T</span>
          <span>S</span>
        </h1>
      </div>

      <main class="main">
        <div class="main__div">

        <div>
          <span>Título:
            <input type="text" v-model="title">
          </span>
        </div>

        <form @submit.prevent="buscar">
          <div>
          <span>Filtro:</span>
            <select name="" v-model="filter">
              <option value="blur">Blur</option>
              <option value="mono">Mono</option>
              <option value="sepia">Sepia</option>
              <option value="negative">Negative</option>
              <option value="paint">Paint</option>
              <option value="pixel">Pixel</option>
            </select>
          </div>
          <div class="colores">
            <span>Color:</span>
            <select name="" v-model="colores">
              <option value="red">Rojo</option>
              <option value="white">Blanco</option>
              <option value="yellow">Amarillo</option>
              <option value="green">Verde</option>
              <option value="black">Negro</option>
              <option value="blue">Azul</option>
            </select>
            <span class="circulo" :style="{backgroundColor : colores}"></span>
          </div>
          <div>
            <span>Tamaño: 
              <input type="text" v-model="size"/>
            </span>
          </div>
          <div class="text-center">
            <button type="submit" class="btn btn-danger p-2 m-3">Obtener Michi</button>
          </div>
        </form>

        </div>
      </main>
    </div>
      
    <section>
      <div>
        <img class="image" :src="url" alt=""/>
      </div>
    </section>

  </div>
</template>

<script>
export default {
  name: 'Gatos',
  data() {
    return {
      title: "",
      filter: "",
      size: "",
      url: "",
      colores: "",
    };
  },

  methods: {
    buscar() {
      let title = this.title;
      let filter = this.filter;
      let colores = this.colores;
      let size = this.size;
      this.url = `https://cataas.com/cat/gif/says/${title}?filter=${filter}&color=${colores}&size=${size}`;
    },
    
  },
};

</script>

<style scoped>
.header {
  width: 100%;
  height: 100px;
  display: flex;
  align-content: center;
  justify-content: center;
}
.header h1 {
  width: 200px;
  margin: 20px;
  background: black;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50px;
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
  background: rgb(75, 207, 207);
  border: 3px solid rgb(0, 0, 0);
  display: flex;
  align-content: center;
  justify-content: center;
}
.main__div {
  width: 100%;
  margin: 20px;
  display: inline-block;
  align-content: center;
  justify-content: center;
}


.image {
  width: 100%;
  height: auto;
  padding: 50px;
}

select, input {
  width: 200px;
  margin: 20px ;
  border-radius: 10px;
  border: 3px solid black;
}
.colores {
  display: flex;
  align-items: center;
}
 .circulo{
   width: 50px;
   height: 50px;
   border-radius: 50%;
   border: 3px solid black;
   background: white;
 }
</style>
