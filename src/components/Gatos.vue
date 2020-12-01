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

        <div>
        <span>Filtro:</span>
          <select name="" v-model="filter">
            <option value="blur">blur</option>
            <option value="mono">mono</option>
            <option value="sepia">sepia</option>
            <option value="negative">negative</option>
            <option value="paint">paint</option>
            <option value="pixel">pixel</option>
          </select>
        </div>

        <div>
          <span>Color:</span>
          <select name="" v-model="color.background">
            <option value="green">Verde</option>
            <option value="red">rojo</option>
            <option value="black">negro</option>
            <option value="white">blanco</option>
            <option value="blue">azul</option>
            <option value="yellow">amarillo</option>
          </select>
          <button :style="color"></button>
        </div>

        <div>
          <span>Tamaño: 
            <input type="text" v-model="size"/>
          </span>
        </div>
        </div>
      </main>

      </div>
      <section>
        <div class="text-center">
          <button @click="buscar" class="btn btn-danger p-2 m-3">Obtener Michi</button>
        </div>
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
      color: {
        background: "",
        padding: "20px 20px",
        borderRadius: "50%",
        margin: "10px",
        border: "3px solid black",
      },
    };
  },

  methods: {
    buscar() {
      let title = this.title;
      let filter = this.filter;
      let colors = this.getcolor;
      let size = this.size;
      this.url = `https://cataas.com/cat/gif/says/${title}?filter=${filter}&color=${colors}&size=${size}`;
    },
    getcolor() {
      return this.color.background;
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
  background: rgb(251, 255, 0);
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
  height: 500px;
  padding: 50px;
}

select, input {
  width: 200px;
  margin: 20px ;
}

</style>
