<template>
    <section>
        <article class="info">
            <h1>Welcome back!</h1>
            <p>Don't fall behind, log in to continue enjoying our diverse selection of artisanal coffees or sign up to start your journey!</p>
            <button class="btn-signup" @click="navigationSignUp">SIGN UP</button>
        </article>
        
        <article class="formulario">
            <p>Log in</p>
            <form @submit.prevent="sendForm">
                <input v-model="username" @blur="usernameValidation" type="text" name="username" placeholder="Username">
                <input v-model="password" @blur="passwordValidation" type="password" name="password" placeholder="Password">
                <span class="error">{{ error }}</span>
                <button type="submit" class="btn-login">LOG IN</button>
            </form>
        </article>
        <img id="foto-home" src="../../../../assets/home-photo.png">
    </section>
</template>

<script>
import router from '@/aromio/router/router';

    export default {
        data() {
            return {
                username: "",
                password: "",
                error: ""
            }
        },
        methods: {
            navigationSignUp() {
                router.push("/signup")
            },

            usernameValidation() {
                if (this.username.trim() === "") {
                    this.error = "Please make sure you fill in all fields"
                    return false
                } else {
                    this.error = ""
                    return true
                }
            },
            passwordValidation() {
                if (this.password.trim() === "" || this.password.length < 5) {
                    this.error = "Please provide a password that is 5 characters or longer"
                    return false
                }
                this.error = ""
                return true
            },
            sendForm() {
                if (this.usernameValidation() && this.passwordValidation()) {
                    router.push("/shop")
                }
            }
        }
    }
</script>

<style scoped>

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        background-color: rgb(243, 239, 238);
    }

    section {
        display: flex;
        width: 100%;
        height: 100%;
    }

    .formulario, .info {
        width: 50%;
        display: flex;
        height: 94.6vh;
        justify-content: center;
    }
    .formulario {
        margin-top: 10vw;
        height: 25vw;
    }

    .btn-login {
        margin-top: 8vh;
        font-family: 'Alata', sans-serif;
        background-color: rgb(73, 30, 18);
        color: white;
        font-size: medium;
        border-radius: 30vh;
        height: 5vh;
        width: 22vh;
        border: none;
        cursor: pointer;
        letter-spacing: 0.13cm;
    }

    .formulario p {
        position: absolute;
        font-family: 'Alata', sans-serif;
        font-size: 1.3vw;
        color: rgb(73, 30, 18);
    }

    .info {
        background-color: rgb(73, 30, 18);
    }

    form {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 43vh;
    }

    input {
        border: none;
        border-bottom: 0.16vw solid rgb(186, 186, 186);
        outline: none;
        margin-top: 1vw;
        margin-bottom: 1vw;
        width: 20vw;
        height: 2vw;
    }

    input::placeholder {
        font-family: 'Alata', sans-serif;
        color: rgb(186, 186, 186);
        font-size: large;
    }

    .error {
        padding: 1vw;
        margin: 0 auto;
        color: rgb(223, 67, 67);
        font-family: 'Alata', sans-serif;
    }

    .info h1, .info p, .info button {
        background-color: rgb(73, 30, 18);
        
    }

    .info {
        display: flex;
        flex-direction: column;
    }

    .btn-signup {
        border: 1px solid rgb(255, 255, 255);
        color: white;
        font-family: 'Alata', sans-serif;
        height: 3vw;
        width: 10vw;
        justify-content: center;
        font-size: 1vw;
        border-radius: 50px;
        letter-spacing: 5px;
        cursor: pointer;
        margin-left: 2vw;
        margin-top: 6vw;
    }
    
    .info p, .info h1 {
        color: white;
    }

    .info p {
        font-family: 'Alata', sans-serif;
        margin-left: 2vw;
        font-size: 1.5vw;
        width: 60%;
    }

    .info h1 {
        font-family: 'Archivo Black', sans-serif;
        font-size: 4vw;
        margin-left: 2vw;
    }

    #foto-home {
        position: absolute;
        bottom: 0;
        margin-left: 41.5vw;
        width: auto;
        height: 45vh;
        background-color: transparent;
        filter: drop-shadow(-24px 26px 30px rgba(0, 0, 0, 0.7));
    }


</style>