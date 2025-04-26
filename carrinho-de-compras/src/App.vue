<script setup> 
</script> 

<template>
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
footer{
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