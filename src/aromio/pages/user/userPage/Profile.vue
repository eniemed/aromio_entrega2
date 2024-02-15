<template>
    <section>
        <article class="user-info-top">
            <div>
                <img src="../../../../assets/user-profile.png" alt="picture">
                <div class="user-info-top-details">
                    <p>Esther Nieto Medina</p>
                    <button @click="homeNavigation">Log out</button>
                </div>
            </div>
        </article>
        <article class="user-info-bottom">
            <section>
                <article>
                    <p>Full name</p>
                    <div>
                        <p>Esther Nieto Medina</p>
                    </div>
                </article>
                <article>
                    <p>Username</p>
                    <div>
                        <p>Username</p>
                    </div>
                </article>
                <article>
                    <p>Email</p>
                    <div>
                        <p>Email@gmail.com</p>
                    </div>
                </article>
            </section>
        </article>
    </section>
</template>

<script>
    import router from "../../../router/router"
    export default {
        methods: {
            homeNavigation() {
                router.push("/")
            }
        }
        
    }
</script>

<style>
    .user-info-top img {
        height: 10vw;
        width: auto;
        background-color: rgb(131, 73, 49);
        padding-left: 1vw;
    }

    .user-info-top div {
        display: flex;
        align-items: center;
        justify-content: space-between;
        background-color: rgb(131, 73, 49);
        font-family: 'Alata', sans-serif;
        color: white;
        width: 50vw;
        height: 15vw;
        margin: 0 auto;
        border-radius: 1.5vw;
    }

    .user-info-top-details {
        display: flex;
        flex-direction: row;
    }

    .user-info-top-details p {
        background-color: rgb(131, 73, 49);
        font-size: 1vw;
    }

    .user-info-top-details p, .user-info-top-details button {
        margin-left: 25px;
    }

    .user-info-top-details button {
        margin-right: 1.2vw;
        margin-top: 11.3vw;
        background-color: rgb(73, 30, 18);
        border: none;
        border-radius: 20px;
        height: 1.7vw;
        width: 5vw;
        color: white;
        font-family: 'Alata', sans-serif;
        font-size: 0.8vw;
        cursor: pointer;
    }

    article>p {
        color: rgb(160, 127, 117);
    }

    .user-info-bottom {
        margin-top: 5vw;
        font-family: 'Alata', sans-serif;
        margin-left: 25vw;
        font-size: 1.1vw;
    }

    .user-info-bottom article div p {
        background-color: rgb(255, 255, 255);
        height: 2vw;
    }



</style>
