<template>
    <section>
        <article class="info">
            <h1>Welcome!</h1>
            <p>Are you ready to join and explore the world of coffee with us?</p>
            <p>Have you signed up already?</p>
            <button class="btn-login" @click="navigationLogIn">LOG IN</button>
        </article>
        
        <article class="formulario">
            <p>Sign up</p>
            <form @submit.prevent="sendForm">
                <input v-model="name" @blur="nameValidation" type="text" name="name" placeholder="First name">
                <span class="error">{{ nameError }}</span>
                <input v-model="lastName" @blur="lastNameValidation" type="text" name="lastName" placeholder="Last name">
                <span class="error">{{ lastNameError }}</span>
                <input v-model="username" @blur="usernameValidation" type="text" name="username" placeholder="Username">
                <span class="error">{{ usernameError }}</span>
                <input v-model="email" @blur="emailValidation" type="email" name="email" placeholder="Email">
                <span class="error">{{ emailError }}</span>
                <input v-model="password" @blur="passwordValidation" type="password" name="password" placeholder="Password">
                <span class="error">{{ passwordError }}</span>
                <button type="submit" class="btn-signup">SIGN UP</button>
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
                name: "",
                lastName: "",
                username: "",
                email: "",
                password: "",
                nameError: "",
                lastNameError: "",
                usernameError: "",
                emailError: "",
                passwordError: "",
                emailRegex: /^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/,
            }
        },
        methods: {
            nameValidation() {
                if (this.name.trim() === "") {
                    this.nameError = "Please write your first name"
                    return false
                }
                this.nameError = ""
                return true
            },
            lastNameValidation() {
                if (this.lastName.trim() === "") {
                    this.lastNameError = "Please write your last name"
                    return false
                }
                this.lastNameError = ""
                return true
            },
            usernameValidation() {
                if (this.username.trim() === "") {
                    this.usernameError = "Please choose your username"
                    return false
                }
                this.usernameError = ""
                return true
            },
            emailValidation() {
                if (this.email.trim() === "" || !this.emailRegex.test(this.email)) {
                    this.emailError = "Please enter a valid email address"
                    return false
                }
                this.emailError = ""
                return true
            },
            passwordValidation() {
                if (this.password.trim() === "" || this.password.length < 5) {
                    this.passwordError = "Please provide a password that is 5 characters or longer"
                    return false
                }
                this.passwordError = ""
                return true
            },
            sendForm() {
                if(this.nameValidation() && this.lastNameValidation() && this.usernameValidation() && this.emailValidation() && this.passwordValidation()) {
                    router.push("/shop")
                }
            },
            navigationLogIn() {
                router.push("/login")
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
        align-items: center;
    }

    .btn-signup {
        margin-top: 2vh;
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
        margin-bottom: 65vh;
        
    }

    .info {
        background-color: rgb(73, 30, 18);
    }

    form {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 43vh;
    }

    input {
        border: none;
        border-bottom: 0.16vw solid rgb(186, 186, 186);
        outline: none;
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

    .btn-login {
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
        margin-top: 2vw;
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

    .info p:nth-child(3){
        font-style: italic;
        margin-top: 6vw;
        font-size: 1.2vw;
    }

</style>