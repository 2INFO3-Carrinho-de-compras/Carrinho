<script setup>
import { reactive, ref } from 'vue';

const carrinho = reactive({
  items: [],
});

const produtos = ref([
  {
    id: 1,
    titulo: 'lamina da assassina',
    autor: 'Sarah.J.Mass',
    preco: 'R$82,46',
    capa: 'https://aishando.home.blog/wp-content/uploads/2023/08/7-1.jpg',
  },
  {
    id: 2,
    titulo: 'Trono de Vidro',
    autor: 'Sarah.J.Mass',
    preco: 'R$72,44',
    capa: 'https://aishando.home.blog/wp-content/uploads/2023/08/81yjssr1ibl.jpg',
  },
  {
    id: 3,
    titulo: 'Coroa da Meia-Noite',
    autor: 'Sarah.J.Mass',
    preco: 'R$104,93',
    capa: 'https://aishando.home.blog/wp-content/uploads/2023/08/81zha4ugo0l.jpg',
  },
  {
    id: 4,
    titulo: 'Herdeira do Fogo',
    autor: 'Sarah.J.Mass',
    preco: 'R$84,48',
    capa: 'https://aishando.home.blog/wp-content/uploads/2023/08/815ugbyzn2l.jpg',
  },
  {
    id: 5,
    titulo: 'Rainha das Sombras',
    autor: 'Sarah.J.Mass',
    preco: 'R$113,30',
    capa: 'https://m.media-amazon.com/images/I/81xKVoXj2jL._SY385_.jpg',
  },
  {
    id: 6,
    titulo: 'Império de Tempestades',
    autor: 'Sarah.J.Mass',
    preco: 'R$111,92',
    capa: 'https://photos.enjoei.com.br/livro-imperio-de-tempestades-edicao-de-luxo-sarah-j-maas-trono-de-vidro-120875157/1200xN/czM6Ly9waG90b3MuZW5qb2VpLmNvbS5ici9wcm9kdWN0cy8zNzkwMTUwNy80ZWM2YjQwZGIwOTRlMTkyYmVkYzQ5N2RmZGI4N2M1OC5qcGc',
  },
  {
    id: 7,
    titulo: 'Torre do alvorecer',
    autor: 'Sarah.J.Mass',
    preco: 'R$89,90',
    capa: 'https://http2.mlstatic.com/D_NQ_NP_2X_637631-MLU77441655237_072024-F.webp',
  },
  {
    id: 8,
    titulo: 'Reino de Cinzas',
    autor: 'Sarah.J.Mass',
    preco: 'R$134,93',
    capa: 'https://img.travessa.com.br/livro/GR/b2/b2696057-9310-4581-8a64-e060625ee84f.jpg',
  },

]);

function adicionarProduto(livro) {
  carrinho.items.push(livro);
}
//function removerProduto(index) {
  //carrinho.items.value.splice(index, 1);
//}
</script>

<template>
  <main>
    <section>
      <div class="conteudo">
        <button class="autor"> Autor de Abril </button>

        <h2>
          Corte de Névoa e Fúria
        </h2>
        <p>
          Após resgatar o seu amado Tamlin do reinado da rainha Amaratha, Feyre regressa <br> a Corte Primaveril com os
          poderes de todos grão-senhores. Mas esquecer os crimes <br> que teve que cometer para salvar o povo de Tamlin,
          se tornou impossível. Entretanto, <br> uma guerra iminente aproxima-se e um mal muito mais perigoso o
          acompanha, <br> que com o tempo provará que 50 anos do reinado de Amaratha, torturas e terror, <br> escravidão
          e medo, eram apenas uma brincadeira de criança… Apenas um mísero <br> teste e prova do que eles eram capazes e
          podiam fazer se desejassem.

        </p>

        <button class="pagina"> Acessar página do livro </button>
      </div>

      <div class="foto">
        <img src="/img/capa.jpeg" alt="capa" width="470" height="620">
      </div>

    </section>

    <hr class="sectopo">

    <section class="opcoes">
      <div>
        <img src="/img/caminhao.png" alt="caminhao" width="50" height="45">
        <p>Frete grátis para SC</p>

      </div>
      <hr>
      <div>
        <img src="/img/estrela.png" alt="estrela" width="50" height="45">
        <p>Livros recomendados</p>

      </div>
      <hr>
      <div>
        <img src="/img/livro.png" alt="livro" width="50" height="45">
        <p>Mais vendidos</p>
      </div>
    </section>
    <hr>
  </main>

  <section class="produtos">
    <ul>
      <li v-for="livro in produtos" :key="livro.id">
        <p v-for="imagem in produtos" :key="imagem.id"></p>

        <p><img :src="livro.capa" alt="" width="200" height="200"></p>
        <p>{{ capa }}</p>
        <p class="titulo"> {{ livro.titulo }}</p>

        <p v-for="autora in produtos" :key="autora.id"></p>
        <p class="autor"> {{ livro.autor }}</p>

        <p v-for="numero in produtos" :key="numero.id"></p>
        <p class="preco">{{ livro.preco }} <i class="fa-solid fa-heart"></i></p>
        <button class="botao" @click= "adicionarProduto" in produtos><a class="fa-solid fa-square-plus"></a> Comprar</button>
      </li>
    </ul>

  </section>
  <section>
      <p v-for="livro in carrinho.items" :key="livro.id"> {{ livro }}</p>
      <p>{{ items }}</p>
      <!-- <p><img :src="livro.capa" alt="" width="200" height="200" ></p> -->
      <!-- <p>{{ capa }}</p> -->
  </section>
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

.conteudo p {
  font-size: 1.2vw;
}

section div.conteudo button.pagina {
  margin: 3.5vw 0 0 0;
  font-size: 1.2vw;
  border: none;
  border-radius: 0.5vw;
  padding: 1vw 2vw 1vw 2vw;
  background: linear-gradient(rgb(211, 34, 137), rgb(212, 71, 154));
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

.opcoes div {
  display: flex;
}

.opcoes div img {
  margin: 0 2vw 0 0;
}

section.produtos ul {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin: 0 2vw;

}

section.produtos li {
  box-sizing: border-box;
  width: 20%;
  margin: 6vw 1vw 0 0;
  padding: 0 1vw;
  white-space: nowrap;
  list-style: none;
}

section.produtos img {
  width: 88%;
  height: 20vw;
}

section.produtos p.titulo {
  font-size: 1.5vw;
  color: black;
  font-family: bold;
}

section.produtos p.preco {
  font-family: bold;
  font-size: 1vw;
  color: black;
}

section.produtos p.preco i {
  margin: 0 0 0 9.5vw;
  font-size: 1.2vw;
}

section.produtos button.botao {
  display: flex;
  justify-content: center;
  margin: 1.7vw 0 0 0;
  padding: 0.7vw 6vw 0.7vw 6vw;
  border: none;
  background: linear-gradient(rgb(211, 34, 137), rgb(212, 71, 154));
  color: white;
  border-radius: 0.5vw;
}

.produtos button.botao a {
  padding: 0 0.5vw 0 0;
  font-size: 1vw;
}
</style>
