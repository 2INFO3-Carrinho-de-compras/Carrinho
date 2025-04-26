<script setup>
</script>

<template>
<header>
    <h1>
        IFbooks
    </h1>
    <p class="titulo">
        Apreço a <br> leitura
    </p>

    <div class="pesquisa">
       <input type="text" class="pesquisa" placeholder="Pesquisar" >
       <a class="lupa">
        <img src="/public/img/icon.png" alt="lupa">
       </a>
    </div>
    
    <div class="topo">
        <ul class="botoes">
            <li>
                <a href="Termos">Termos</a>
            </li>
            <li>
                <a href="Equipe">Equipe</a>
            </li>
            <li>
                <a href="Envio">Envio</a>
            </li>
            <li>
                <a href="Devoluções">Devoluções</a>
            </li>
        </ul>
        <ul class="icones">
            <li>
                <a class="fa-solid fa-square-plus"></a>
            </li>
            <li>
                <i class="fa-solid fa-heart"></i>
            </li>
            <li>
                <i class="fa-solid fa-user"></i>
            </li>
        </ul>
    </div>
</header>
</template>

<style scoped>
header {
    display: flex;
    border-bottom:2px solid rgb(211, 34, 137);
}
h1{
    padding: 0 10px 0 0;
    font-size: 1.5vw;
    margin: 1.5vw 0 1.5vw 8vw;
    color: black;
}
.pesquisa{
    display: flex;
    border-radius: 20px;
    border: none;
    background-color: rgb(252, 225, 240);
    margin: 1vw;
}
.pesquisa input{
    padding: 5px 10vw 5px 1vw;
}
.pesquisa a.lupa{
  padding: 3px 1vw 0 0;
  margin: 1vw 0 1vw 0;
}
div.topo{
    display: flex;
}
div.topo ul.botoes{
    display: flex;
}
div.topo ul.icones{
    display: flex;
}
div.topo ul.botoes li {
    margin: 2vw 2vw 1vw 1vw;
    list-style: none;
}
.icones li{
    margin: 2vw 1vw 1vw 0;
    list-style: none;
}
.icones li i{
    border-left:2px solid rgb(211, 34, 137);
    color: rgb(211, 34, 137);
    font-size: 1.3vw;
    padding: 0 0 0 20px;
}
.icones li a{
    color: rgb(211, 34, 137);
    font-size: 1.3vw;
}
header p {
    display: flex;
    margin: 1vw 0 0 0;
}
a {
    color: gray;
    text-decoration: none;
}
header p.titulo{
    padding: 0 0 0 10px;
    font-size: 1vw;
    margin: 1.5vw 8vw 1vw 0;
    color: rgb(211, 34, 137);
    border-left:2px solid rgb(211, 34, 137);
}
</style>