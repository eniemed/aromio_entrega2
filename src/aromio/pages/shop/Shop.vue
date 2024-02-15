<template>
    <section class="fondo">
        <article class="contenedor-cards">
            <div v-for="product in products" :key="product.name" class="card">
                <img class="imagen" :src="product.image" :alt="product.name">
                <p class="nombre">{{ product.flavor_name }}</p>
                <h3 class="titulo">{{ product.name }}</h3>
                <span class="precio">{{ product.price }}</span>
                <div class="contenedor-btn">
                    <button class="añadir-carrito">Add to cart ⟶</button>
                    <button class="favoritos">♡</button>
                </div>
            </div>
        </article>
    </section>
</template>

<script>
export default {
    data() {
        return {
            products: []
        }
    },
    mounted() {
        this.getProducts()
    },
    methods: {
        async getProducts() {
            try {
                const res = await fetch("http://localhost:8000/api/products")
                const data = await res.json()
                this.products = data
            } catch (error) {
                console.error(error)
            }
        }
    }
}
</script>

<style>
    .card {
        background-color: white;
        width: 30vh; /* Establece el ancho de cada tarjeta para mostrar 4 tarjetas en una fila */
        height: 20vw;
        margin-bottom: 200px; /* Añade margen inferior a cada tarjeta */
        text-align: center;
        border-radius: 8px;
        padding: 10px;
    }

.contenedor-cards {
    padding: 30vh;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}

.imagen {
    background-color: transparent;
    width: 100%; /* Asegura que la imagen ocupe el ancho completo de la tarjeta */
    height: 35vh;
    object-fit: cover; /* Ajusta el comportamiento de la imagen para cubrir el contenedor */
    border-radius: 8px;
    display: block; /* Evita posibles márgenes adicionales */
    margin: -150px 0 auto;
}

    .nombre,
    .titulo,
    .precio {
        font-family: 'Alata', sans-serif;
        margin: 10px 0;
        background-color: white;
    }

    .precio {
    font-family: 'Alata', sans-serif;
    margin: 10px 0;
    background-color: white;
    margin-top: 20px; /* Ajusta la separación entre el precio y el resto de la información */
}

.añadir-carrito,
.favoritos {
    padding: 8px;
    cursor: pointer;
    border: none;
    background-color: white;
    border-radius: 4px;
    margin-top: 8px; /* Ajusta el margen superior entre el precio y los botones */
}

.contenedor-btn {
    background-color: white;
    display: flex;
    justify-content: space-between; /* Distribuye los elementos a los extremos del contenedor */
    align-items: flex-end; /* Alinea los elementos en la parte inferior del contenedor */
    margin-top: 10px; /* Ajusta el margen superior entre el precio y los botones */
}

.añadir-carrito {
    font-family: 'Alata', sans-serif;
    padding: 8px;
    cursor: pointer;
    border: none;
    background-color: white;
    border-radius: 4px;
}

.favoritos {
    padding: 8px;
    cursor: pointer;
    border: none;
    background-color: white;
    border-radius: 4px;
    color: red;
}
</style>
