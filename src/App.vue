<template>
<img alt="Vue logo" src="./assets/logo.png">
<MiTitulo :titulo="Titulo" />
<ContenedorList/>
</template>

<script>
import MiTitulo from './components/MiTitulo';
import ContenedorList from './components/ContenedorList.vue';
export default {
    name: 'App',
    data() {
        return {
            Titulo: "Bienvenido A Todo List Con Vue CLI"
        }
    },
    components: {
        MiTitulo,
        ContenedorList
    }
}
</script>
<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
@import "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.8.2/css/all.css";
*{
    margin: 0;
    padding: 0;
    font-family: "montserrat",sans-serif;
    box-sizing: border-box;
}

body{
    background-image: linear-gradient(120deg,#487eb0,#fbc531);
    min-height: 100vh;
}
</style>
