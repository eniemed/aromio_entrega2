<template>
    <header>
        <router-link to="/"><img src="../../assets/logo.png" alt="Página principal de Aromio"></router-link>

        <nav>
            <ul id="links">
                <li><router-link to="/">Home</router-link></li>
                <li><router-link to="/shop">Shop</router-link></li>
                <li><router-link to="/wishlist">Wishlist</router-link></li>
                <li><router-link to="/contact">Contact</router-link></li>
            </ul>
        </nav>

        <nav>
            <ul id="auth">
                <li><router-link to="/login">Log in</router-link></li>
                <li><router-link to="/signup"><button class="btn-marron">Sign up</button></router-link></li>
            </ul>
        </nav>
    </header>
</template>

<script>
    export default {
     
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Alata&family=Archivo+Black&display=swap');

    * {
        margin: 0%;
        padding: 0%;
        box-sizing: border-box;
        background-color: rgb(243, 239, 238);
    }

    header {
        width: 100%;
        padding: 1rem;
        display: flex;
        justify-content: space-between;
        align-items: center;
        font-family: 'Alata', sans-serif;
        height: 50px;
    }

    img {
        height: 50px;
    }

    button {
        font-size: 1.5vh;
    }

    ul {  
        list-style: none;
        display: flex;
    }

    a {
        text-decoration: none;
        color: rgb(56, 56, 56);
    }

    #links li {
        margin-left: 60px;
        transition: all 0.3s;
        
    }

    #links li:hover {
        transform: scale(1.2);
    }

    #auth {
        align-items: center;
    }

    #auth li {
        margin-left: 25px;
    }

    .btn-marron {
        color: white;
        background-color: rgb(73, 30, 18);
        font-family: 'Alata', sans-serif;
        cursor: pointer;
        height: 35px;
        width: 100px;
        border-radius: 50vh;
        border: none;
    }

</style>