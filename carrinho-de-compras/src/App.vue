<script setup>
</script>

<template>
  <header>
    <h1>
  IFbooks
 </h1>
    <p class="pesquisar">
      Pesquisar
    </p>
 <div class="topo">
<ul>
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

    <li>
      <i class="fa-solid fa-square-plus"></i>
    </li>
    <hr>

    <li>
      <i class="fa-solid fa-heart"></i>
    </li>
    <hr>

    <li>
      <i class="fa-solid fa-user"></i>
    </li>
</ul>
 </div>
</header>

<hr>
<main>
  <section>
    <div class="conteudo">
      <button class="autor"> Autor de Abril </button>
        
      
      <h2>
        Eric-Emanuel Schmitt
      </h2>
      <p>
        Eric-Emmanuel Schmitt has been awarded more than 20 <br> literary prizes and distinctions, and in 2001 he received the <br> title of Chevalier des Arts et des Lettres. His books have been <br> translated into over 40 languages.
      </p>

      <button class="pagina"> Acessar página do livro </button>
    </div>

    <div class="foto">

      <img public="img/lamina_da.jpg" width="400" height="435">

    </div>

  </section>

  <hr class="sectopo">

  <section class="opcoes">
    <div>
      <p><i class="fa-solid fa-truck-medical"></i> Frete grátis para SC</p>
      
    </div>
    <hr>
    <div>
      <p> <i class="fa-solid fa-star"></i> Livros recomendados</p>

    </div>
    <hr>
    <div>
      <p><i class="fa-solid fa-book-open"></i> Mais vendidos</p>

    </div>

  </section>
    <hr>
 </main>


</template>

<style scoped>
header {
  display: flex;
  justify-content: space-around;
}
p.pesquisar {
  background-color: gray;
  color: rgb(90, 87, 87);
}
div.topo ul{
  display: flex;
  padding: 1vw 0 0 0;
}
div.topo ul li {
  margin: 0 3vw 0 0;
  list-style: none;
}
header p {
  display: flex;
  margin: 1vw 25vw 0 0;
}
a {
  color: black;
  text-decoration: none;
}
div.topo ul hr{
  margin: 0 0.5vw 0 0.5vw;
}
hr {
  border-color: rgb(194, 28, 194);
}
i {
  color: rgb(194, 28, 194);
}


 section {
  display: flex;
  justify-content: space-around;
  
}
section div.conteudo button.autor {
  margin: 10vw 0 3.5vw 0;
  padding: 0.7vw ;
  border-color: rgb(194, 28, 194);
  background-color: white;
  color: rgb(194, 28, 194);
}
section div.conteudo h2 {
  font-size: 3rem;
  font-weight: bold;
  color: black;
  margin: 0 0 2vw 0;
}
section div.conteudo button.pagina {
  margin: 3.5vw 0 0 0;
  font-size: 1.2vw;
  border-radius: 0.5vw;
  padding: 1vw 2vw 1vw 2vw ;
  background: linear-gradient(rgb(137, 13, 141) , rgb(194, 28, 194));
  color: white;
}
section div.foto {
  display: flex;
  justify-content: left;
  margin: 6vw 2vw 0 0;
}
hr.sectopo {
  margin: 6vw 0 0 0;
}
section.opcoes {
  margin: 4vw 0 4vw 0;
}
section.opcoes hr {
  margin: -1vw;
}
</style>