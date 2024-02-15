<template>
    <body>
        <section>
            <article class="info-home">
                <p class="info-home-titulo">AROMIO</p>
                <p class="info-home-texto">Your morning coffee only a click away! Choose your type to wake up with full energy.</p>
                <button @click="navigationShop">Explore our products</button>
            </article>
            <article class="info-caracteristicas">
                <table>
                    <thead>
                        <tr>
                            <th>Flavors</th>
                            <th>Roast levels</th>
                            <th>Grind options</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>+ 30</td>
                            <td>5</td>
                            <td>7</td>
                        </tr>
                    </tbody>
                </table>
            </article>
            <article class="contenedor-foto-home">
                <img class="img-decorative" src="../../assets/decoration-home.svg" alt="">
                <img id="foto-home" src="../../assets/home-photo.png" alt="">
            </article>
        </section>

    </body>
</template>
<script>
import router from "../router/router"
export default {
    methods: {
        navigationShop() {
            router.push("/shop")
        }
    }

}
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Alata&family=Archivo+Black&display=swap');

.img-decorative {
    position: absolute;
    margin-top: 10.5vw;
    top: 0;
    right: 0;
    background-color: rgb(230, 222, 219);
    height: 19vw;
    width: 32vw;
    border-bottom-left-radius: 50px;
    border-top-left-radius: 50px;
}
.info-home {
    display: flex;
    flex-direction: column;
    width: fit-content;
    height: auto;
    padding: 6vw;
    margin-left: 8.3vw;

}

.info-caracteristicas {
    position: absolute;
}

.contenedor-foto-home {
    position: relative;
    align-self: flex-end;
    margin-top: -60vh;
    position: relative;
    z-index: 1;
}

.info-home-texto {
    font-family: 'Alata', sans-serif;
    font-size: large;
    color: rgb(83, 57, 49);
    width: 34%;

}

.info-home-titulo {
    display: flex;
    font-family: 'Archivo Black', sans-serif;
    font-size: 14vh;
    color: rgb(83, 57, 49);
}

.info-home button {
    margin-top: 80px;
    font-family: 'Alata', sans-serif;
    background-color: rgb(73, 30, 18);
    color: white;
    font-size: 16px;
    border-radius: 40px;
    height: 47px;
    width: 180px;
    border: none;
    cursor: pointer;
}

#foto-home {
    position: absolute;
    top: 0;
    right: 0;
    margin-top: 5.8vw;
    margin-right: 9vw;
    width: auto;
    height: 60vh;
    background-color: transparent;
    filter: drop-shadow(-24px 26px 30px rgb(72, 72, 72));
}

/* div {
    position: absolute;
    margin-top: 10.5vw;
    top: 0;
    right: 0;
    background-color: rgb(230, 222, 219);
    height: 19vw;
    width: 32vw;
    border-bottom-left-radius: 50px;
    border-top-left-radius: 50px;
} */



table {
    margin-left: 9.2vw;
    color: rgb(57, 18, 7);

}

th, td {
    padding-left: 100px;
    padding-bottom: 40px;
    text-align: center;
}

th {
    font-family: 'Archivo Black', sans-serif;
    font-size: 1vw;
}

td {
    text-align: center;
    font-family: 'Alata', sans-serif;
    color: rgb(56, 56, 56);
    font-weight: 700;
    font-size: 1vw;
}

.container {
    display: flex;
    flex-direction: column;
    position: relative;
}

.info-home, .info-caracteristicas, .contenedor-foto-home {
    width: 100%;
}
</style>