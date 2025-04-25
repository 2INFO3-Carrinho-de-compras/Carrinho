<script setup>
</script>

<template>
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
      <img src="/public/img/capa.jpeg" alt="capa" width="470" height="620">
    </div>

  </section>

  <hr class="sectopo">

  <section class="opcoes">
    <div>
      <img src="/public/img/caminhao.png" alt="caminhao" width="50" height="45"> <p>Frete grátis para SC</p>

    </div>
    <hr>
    <div>
      <img src="/public/img/estrela.png" alt="estrela" width="50" height="45"> <p>Livros recomendados</p>

    </div>
    <hr>
    <div>
      <img src="/public/img/livro.png" alt="livro" width="50" height="45"> <p>Mais vendidos</p>
    </div>

  </section>
    <hr>
 </main>


</template>

<style scoped>
hr {
  border-color: rgb(211, 34, 137);
}
i {
  color: rgb(211, 34, 137);
}
 section {
  display: flex;
  justify-content: space-around;
}
section div.conteudo button.autor {
  font-size: 0.8vw;
  margin: 10vw 0 2.7vw 0;
  padding: 0.7vw;
  border-color: rgb(211, 34, 137);
  background-color: white;
  color: rgb(211, 34, 137);
}
section div.conteudo h2 {
  font-size: 3.5rem;
  font-weight: bold;
  color: black;
  margin: 0 0 2vw 0;
}
.conteudo p{
  font-size: 1.2vw;
}
section div.conteudo button.pagina {
  margin: 3.5vw 0 0 0;
  font-size: 1.2vw;
  border: none;
  border-radius: 0.5vw;
  padding: 1vw 2vw 1vw 2vw ;
  background: linear-gradient(rgb(211, 34, 137) , rgb(212, 71, 154));
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
section.opcoes p {
  font-size: 1.5vw;
  margin: 0 1vw 0 0;
}
.opcoes div{
  display: flex;
}
.opcoes div img{
  margin: 0 2vw 0 0;
}
</style>