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
    <input type="text" class="pesquisa" placeholder="Pesquisar" >     
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

<main>   
    <section>     
        <div class="Conteudo">       
            <button>         
                Autor de Abril       
            </button>       
            <h2>         
                Eric-Emanuel Schmitt       
            </h2>       
            <p>         
                Eric-Emmanuel Schmitt has been awarded more than <br> 20 literary prizes and distinctions, and in 2001 he received the <br> title of Chevalier des Arts et des Lettres. His books have been translated into over <br> 40 languages.       
            </p>       
            <button>         
                Acessar página do livro       
            </button>     
        </div>   
    </section>  
</main> 
</template>

<style scoped> 
header {   
    display: flex;   
    border-bottom:2px solid rgb(76, 196, 76); 
} 
h1{   
    padding: 0 10px 0 0;   
    font-size: 1.5vw;   
    margin: 1.5vw 0 1.5vw 8vw;
    color: black; 
} 
header input{   
    border-radius: 2px;   
    border: none; 
    background-color: rgb(235, 235, 235);   
    padding: 0 12vw 0 1vw;   
    margin: 1.5vw 0 1.5vw 0; 
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
    margin: 1.7vw 2vw 1vw 1vw;   
    list-style: none; 
}
.icones li{
    margin: 1.7vw 1vw 1vw 0;   
    list-style: none; 
}
.icones li i{
    border-left:2px solid rgb(76, 196, 76);
    color: rgb(76, 196, 76);
    font-size: 1.3vw;
    padding: 0 0 0 20px;
} 
.icones li a{
    color: rgb(76, 196, 76);
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
    margin: 1vw 8vw 1vw 0;   
    color: rgb(76, 196, 76);   
    border-left:2px solid rgb(76, 196, 76); 
} 
section {   
    display: flex;   
    justify-content: space-around; 
} 
section div.foto {   
    display: flex;   
    justify-content: left;
} 
</style>