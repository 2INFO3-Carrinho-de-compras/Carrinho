<script setup>
import { ref } from 'vue';

const carrinho = ref([]);

const curtidos = ref([]);

const mostrarTexto = ref(false);

const mostrarPagina = ref(false);

const produtos = ref([
  {
    id: 1,
    titulo: 'Lamina da assassina',
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

function adicionarProduto(book) {
  const existente = carrinho.value.find((p) => p.id === book.id);
  if (existente) {
    existente.quantidade++;
  } else {
    carrinho.value.push({ ...book, quantidade: 1 });
  }
}

function alternarTexto(){
  mostrarTexto.value = !mostrarTexto.value;
}

function removerProduto(book) {
  const index = carrinho.value.findIndex((p) => p.id === book.id);
  if (index !== -1) {
    carrinho.value.splice(index, 1);
  }
}

function incrementar(book){
    book.quantidade++
}

function decrementar(book){
    if(book.quantidade > 1){
        book.quantidade--
    }
}

function subPreco(book) {
   return book.quantidade * parseFloat(book.preco.replace('R$', '').replace(',', '.'));
}

function totalCompra() {
  return carrinho.value.reduce((total, item) => {
    return total + subPreco(item);
  }, 0);
}

function adicionarCurtidos(book) {
  const existente = curtidos.value.find((p) => p.id === book.id);
  if (!existente) {
    curtidos.value.push(book);
  }
}

function removerCurtidos(book) {
  const index = curtidos.value.findIndex((p) => p.id === book.id);
  if (index !== -1) {
    curtidos.value.splice(index, 1);
  }
}

function alternarPagina(){
  mostrarPagina.value = !mostrarPagina.value;
}
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
            <img src="/img/Icon.png" alt="lupa">
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
                    <button @click="alternarTexto"><a class="fa-solid fa-square-plus"></a></button>
                </li>
                <li>
                    <button @click="alternarPagina"><i class="fa-solid fa-heart"></i></button>
                </li>
                <li>
                    <i class="fa-solid fa-user"></i>
                </li>
            </ul>
        </div>
    </header>

  <main>
    <ul v-if="mostrarPagina" class="paginaFavorito">
      <h1>Favoritos</h1>

      <p v-if="curtidos.length === 0">Você ainda não tem favoritos!</p>

      <li v-else>
      <li v-for="book in curtidos" :key="book.id">
      <div class="paginaCurtido">
        <p><img :src="book.capa" alt="" width="120" height="150"> {{ capa }}</p>
        <div class="infoLivro">
            <p class="tituloCarrinho">{{ book.titulo }}</p>
            <p> {{ book.autor }}</p>
            <p class="precoCarrinho">{{ book.preco }}</p>
        </div>
         <button class="remover2" @click="removerCurtidos(book)">Remover</button>
      </div>
      </li>
      </li>
    </ul>

    <ul v-if="mostrarTexto" class="paginaCarrinho">
      <h1>Carrinho</h1>

      <p v-if="carrinho.length === 0">Seu carrinho está vazio!</p>

    <li v-else class="informacao">
      <div class="titulos">
        <p class="titulo2">
          Título
        </p>
        <p>
          Quantidade
        </p>
        <p>
          Subtotal
        </p>
      </div>

          <li v-for="book in carrinho" :key="book.id">
            <div class="informacoes">
                <p><img :src="book.capa" alt="" width="120" height="150"> {{ capa }}</p>

                <div class="infoLivro">
                    <p class="tituloCarrinho">{{ book.titulo }}</p>
                    <p class="autorCarrinho"> {{ book.autor }}</p>
                    <p class="precoCarrinho">{{ book.preco }}</p>
                </div>

                <div class="contador">
                    <button class="botoesContador" @click="decrementar(book)">-</button>
                    {{ book.quantidade }}
                    <button class="botoesContador" @click="incrementar(book)">+</button>
                    
                    <button class="remover" @click="removerProduto(book)">Remover</button>
                </div>
                <p class="subPreco">R$ {{ subPreco(book).toFixed(2) }}</p>
            </div>
          </li>
    </li>

      <div class="total">
        <ul>
          <h2>Total da compra:</h2>
          <li>
              Produtos: R$ {{ totalCompra().toFixed(2) }}
          </li>
          <li>
              Frete: R$ 0.00
          </li>
          <li>
              Total: R$ {{ totalCompra().toFixed(2) }}
          </li>
          <button>Ir para o pagamento</button>
        </ul>
      </div>
</ul>

<ul v-if="!mostrarPagina && !mostrarTexto">
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
        <img src="/img/caminhao.png" alt="caminhao" width="50" height="45"><p>Frete grátis para SC</p>
      </div>
      <hr>
      <div>
        <img src="/img/estrela.png" alt="estrela" width="50" height="45"><p>Livros recomendados</p>
      </div>
      <hr>
      <div>
        <img src="/img/livro.png" alt="livro" width="50" height="45"><p>Mais vendidos</p>
      </div>
    </section>
    <hr>

  <section class="produtos">
    <ul>
      <li v-for="livro in produtos" :key="livro.id">

        <p><img :src="livro.capa" alt="" width="200" height="200"></p>
        <p>{{ capa }}</p>
        <p class="titulo"> {{ livro.titulo }}</p>

        <p v-for="autora in produtos" :key="autora.id"></p>
        <p class="autor"> {{ livro.autor }}</p>

        <p v-for="numero in produtos" :key="numero.id"></p>
        <p class="preco">{{ livro.preco }}</p>

        <div v-if="curtidos.find(p => p.id === livro.id)">
          <button class="curtido"><i class="fa-solid fa-heart"></i></button>
        </div>
        <div v-else>
          <button class="curtir" @click="adicionarCurtidos(livro)"><i class="fa-solid fa-heart"></i></button>
        </div>

        <div v-if="carrinho.find(p => p.id === livro.id)">
          <button class="botao"> <a class="fa-solid fa-square-plus"></a> Comprado</button>
        </div>
        <div v-else>
          <button class="comprar" @click="adicionarProduto(livro)"><a class="fa-solid fa-square-plus"></a> Comprar</button>
        </div>
      </li>
    </ul>
  </section>
</ul>
</main>
    <footer>
        <div class="superior">
            <div class="esquerda">
                <h2>
                    IFbooks
                </h2>
                <ul>
                    <li>
                        <i class="fa-brands fa-square-facebook"></i>
                    </li>
                    <li>
                        <i class="fa-brands fa-instagram"></i>
                    </li>
                    <li>
                        <i class="fa-brands fa-square-twitter"></i>
                    </li>
                </ul>
            </div>

            <div class="direita">
                <h2>
                    Contato
                </h2>
                <ul class="contato">
                    <li>
                        <i class="fa-solid fa-hashtag"></i> 
                        <p>+55 47 40045263</p>               
                    </li>
                    <li>
                        <i class="fa-solid fa-clock"></i>
                        <p>8h às 23h - Seg a Sex</p>
                    </li>
                    <li>
                        <i class="fa-solid fa-envelope"></i>
                        <p>contato@ifbooks.com</p>
                    </li>
                </ul>

                <ul class="pagamento">
                    <li>
                        <img src="/public/img/paipal.png" alt="paypal">
                    </li>
                    <li>
                        <img src="/public/img/MasterCard-Logo.png" alt="mastercard">
                    </li>
                    <li>
                        <img src="/public/img/VISA-card-logo.png" alt="visa">
                    </li>
                </ul>
            </div>
        </div>
        <div class="inferior">
            <p>© Alguns direitos reservados. IFbooks 2025. </p>
        </div>
    </footer>
</template>

<style scoped>
/*=============================
        FEAT-1 - HEADER
=============================*/
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
    cursor: pointer;
}
.pesquisa input{
    padding: 5px 10vw 5px 1vw;
}
.pesquisa a.lupa{
  padding: 5px 1vw 0 0;
  margin: 1.3vw 0 1vw 0;
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
.icones button{
  border: none;
  background-color: white;
  cursor: pointer;
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

/*=========================
     FEAT-2 - CONTEÚDO
========================*/

hr {
  border-color: rgb(211, 34, 137);
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
  cursor: pointer;
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
  cursor: pointer;
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

p.titulo {
  font-size: 1.5vw;
  color: black;
  font-family: bold;
}

p.preco {
  font-family: bold;
  font-size: 1.2vw;
  color: black;
}

ul li button.botao {
  display: flex;
  justify-content: center;
  margin: 1.7vw 0 0 0;
  padding: 0.7vw 6vw 0.7vw 6vw;
  border: none;
  background: linear-gradient(rgb(211, 34, 43), rgb(212, 71, 90));
  color: white;
  border-radius: 0.5vw;
  cursor: pointer;
}

.produtos button.botao a {
   padding: 0 0.5vw 0 0;
   font-size: 1vw;
   color: white;
}

ul li button.comprar {
  display: flex;
  justify-content: center;
  margin: 1.7vw 0 0 0;
  padding: 0.7vw 6vw 0.7vw 6vw;
  border: none;
  background: linear-gradient(rgb(211, 34, 137), rgb(212, 71, 154));
  color: white;
  border-radius: 0.5vw;
  cursor: pointer;
}

.produtos button.comprar a {
   padding: 0 0.5vw 0 0;
   font-size: 1vw;
   color: white;
}

ul li button.curtir {
  display: flex;
  justify-content: center;
  margin: 1vw 0 0 0;
  padding: 0.3vw 0.7vw 0.3vw 0.7vw;
  border: none;
  background-color: rgb(255, 169, 219);
  color: rgb(194, 16, 120);
  border-radius: 0.5vw;
  cursor: pointer;
}

ul li button.curtido {
  display: flex;
  justify-content: center;
  margin: 1vw 0 0 0;
  padding: 0.3vw 0.7vw 0.3vw 0.7vw;
  border: none;
  background-color: rgb(255, 131, 137);
  color: rgb(184, 7, 16);
  border-radius: 0.5vw;
  cursor: pointer;
}
/*================================
        FEAT-2 - CARRINHO
================================*/
.remover {
  display: flex;
  justify-content: center;
  margin: 1vw 0 0 0;
  padding: 0.2vw 0.5vw 0.2vw 0.5vw;
  border: none;
  background: linear-gradient(rgb(211, 34, 137), rgb(212, 71, 154));
  color: white;
  border-radius: 0.3vw;
  cursor: pointer;
}

.botoesContador{
  border: none;
  background: linear-gradient(rgb(211, 34, 137), rgb(212, 71, 154));
  color: white;
  border-radius: 0.3vw;
  cursor: pointer;
  padding: 0.2vw 0.5vw 0.2vw 0.5vw;
}

.titulos{
  display: flex;
  border-bottom: 2px solid rgb(211, 34, 137);
  margin: 0 5vw 0 5vw;
}
.titulos p{
  margin: 2vw 5vw 2vw 15vw;
  font-size: 1.3vw;
  font-weight: 500;
}
.titulos p.titulo2{
  margin: 2vw 25vw 2vw 3vw;
  font-size: 1.3vw;
  font-weight: 500;
}

p.tituloCarrinho {
  font-size: 1.5vw;
  color: black;
  font-family: bold;
}

p.precoCarrinho {
  font-family: bold;
  font-size: 1.2vw;
  color: black;
}

.informacoes{
  display: flex;
  margin: 2vw 5vw 2vw 3vw;
}
.informacao{
  list-style: none;
}
.paginaCarrinho h1{
  font-size: 2vw;
  font-weight: 500;
  color: rgb(211, 34, 137);
  margin: 6vw 0 4vw 8vw;
}

.infoLivro{
  margin: 0 0 0 2vw;
}

.contador{
  margin: 2vw 0 0 25vw;
}

.subPreco{
  margin: 2vw 0 0 21.5vw;
  font-size: 1.5vw;
  font-weight: 540;
  font-family: bold;
}

.total{
  border: 2px solid rgb(66, 66, 66);
  margin: 10vw 65vw 2vw 5vw;
}

.total h2{
  font-size: 1.3vw;
  font-weight: 500;
  margin: 2vw 3vw 0 0;
}

.total li{
  border-bottom: 1px solid gray;
  list-style: none;
  margin: 2vw 3vw 0 0;
  font-weight: 500;
}

.total button{
  margin: 2vw 2vw 1.5vw 4vw;
  border: none;
  background: linear-gradient(rgb(211, 34, 137), rgb(212, 71, 154));
  color: white;
  border-radius: 0.2vw;
  cursor: pointer;
  padding: 0.7vw 2vw 0.7vw 2vw;
}

.informacao li{
  border-bottom: 1px solid gray;
  margin: 2vw 5vw 0 5vw;
}

.paginaFavorito{
  list-style: none;
}

.paginaCurtido{
  display: flex;
  margin: 2vw 5vw 2vw 3vw;
}

.paginaFavorito h1{
  font-size: 2vw;
  font-weight: 500;
  color: rgb(211, 34, 137);
  margin: 6vw 0 4vw 8vw;
}

.paginaFavorito li{
  border-bottom: 1px solid gray;
  margin: 2vw 5vw 0 2.5vw;
}
.remover2 {
  display: flex;
  justify-content: center;
  margin: 5vw 2vw 5vw 40vw;
  padding: 0.7vw 5vw 0.7vw 5vw;
  border: none;
  background: linear-gradient(rgb(211, 34, 137), rgb(212, 71, 154));
  color: white;
  border-radius: 0.3vw;
  cursor: pointer;
}
/*===============================
        FEAT-3 - FOOTER
=============================*/

footer{
  margin: 10vw 0 0 0;
    background-color: rgb(211, 34, 137);
    color: white;
}
.superior{
    display: flex;
    justify-content: space-between;
}
.inferior{
    text-align: center;
    margin: 5vw 0 0 0;
    padding: 1.5vw 0 1.5vw 0;
    border-top: 1px solid white;
    color: rgb(255, 145, 209);
}
.esquerda{
    margin: 2vw 0 0 6vw;
}
.esquerda h2{
    font-size: 1.3vw;
    margin: 0 0 0.5vw 2.7vw;
}
.esquerda ul{
    display: flex;
    list-style: none;
}
.esquerda ul li{
    font-size: 2vw;
    margin: 0 2vw 0 0;
}
.direita{
    margin: 2vw 0 0 10vw;
}
.direita h2{
    font-size: 1.3vw;
    margin: 0 0 0.5vw 2.7vw;
    font-weight: bold;
}
.direita ul.contato{
    list-style: none;
}
.direita ul.contato li{
    display: flex;
    margin: 0 2vw 0 0;
    padding: 0 2vw 0 0;
}
.direita ul.contato li i{
    padding: 1.2vw 1vw 0 0;
}
.direita ul.contato li p{
    padding: 0.7vw 2vw 0 0;
}
.direita ul.pagamento{
    list-style: none;
    display: flex;
}
.direita ul.pagamento li{
    margin: 7vw 0 0 0;
    padding: 0 1vw 0 0;
}
</style> 
