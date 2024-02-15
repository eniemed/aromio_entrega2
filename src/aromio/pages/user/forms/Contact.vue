<template>
  <section>
    <article>
      <p id="contact-title">Contact us</p>
      <p id="contact-text">Feel free to contact us anytime. We will get back to you as soon as we can!</p>
      <form @submit.prevent="sendForm">
        <input v-model="email" type="email" name="email" @blur="emailValidation" placeholder="Email">
        <span class="error">{{ emailError }}</span>
        <textarea v-model="text" name="text" @blur="textValidation" placeholder="Message"></textarea>
        <span class="error">{{ textError }}</span>
        <button type="submit">SEND</button>
      </form>
    </article>
    <article>
      <div>
        <p>Info</p>
        <ul id="info-icons">
          <li><img src="../../../../assets/mensaje.png"></li>
          <li><img src="../../../../assets/telf.png"></li>
          <li><img src="../../../../assets/edificio.png"></li>
          <li><img src="../../../../assets/reloj.png"></li>
        </ul>
        <ul id="info-data">
          <li>info@aromio.com</li>
          <li>+34 956 88 77 66</li>
          <li>18 Coffee Lover St.</li>
          <li>9:00 - 16:00</li>
        </ul>
      </div>
      <img class="beans" src="../../../../assets/beans-photo.png">
    </article>
  </section>
</template>
  
<script>
import router from "../../../router/router";

export default {
  data() {
    return {
      email: "",
      text: "",
      emailRegex: /^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/,
      emailError: "",
      textError: ""
    }
  },
  methods: {
    emailValidation() {
      if (this.email.trim() === "" || !this.emailRegex.test(this.email)) {
        this.emailError = "Invalid email address"
        return false
      } else {
        this.emailError = ""
        return true
      }
    },
    textValidation() {
      if (this.text.trim() === "") {
        this.textError = "Please write a message"
        return false
      } else {
        this.textError = ""
        return true
      }
    },
    sendForm() {
      if (this.emailValidation() && this.textValidation()) {
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

  .beans {
    background-color: transparent;
    position: absolute;
    bottom: 0;
    margin-bottom: 2vw;
    margin-left: 5.5vw;
  }

  ul {
    background-color: rgb(73, 30, 18);
  }

  li img {
    background-color: rgb(73, 30, 18);
  }

  #info-icons li {
    display: flex;
    list-style: none;
    background-color: rgb(73, 30, 18);
    margin-top: 2vw;
    margin-left: -9vw;
  }

  #info-icons img {
    background-color: rgb(73, 30, 18);
    width: 2.2vw;
  }

  #info-icons {
    margin-top: 13vw;
    display: flex;
    flex-direction: column;
    background-color: rgb(73, 30, 18);
    width: 2.2vw;

  }

  #info-data li {
    background-color: rgb(73, 30, 18);
    list-style: none;
    color: white;
    font-family: 'Alata', sans-serif;
    margin-top: 3vw;
    font-size: 1vw;
  }

  #info-data {
    margin-top: 12.2vw;
    display: flex;
    flex-direction: column;
    margin-left: -7vw;
  }

  section {
    display: flex;
    width: 80%;
    margin-left: 20%;
  }


  div {
    background-color: rgb(73, 30, 18);
    width: 30vw;
    height: 90%;
    display: flex;
    align-content: center;
    margin-left: auto;

  }

  div>p:first-child {
    background-color: rgb(73, 30, 18);
    color: white;
    font-family: 'Archivo Black', sans-serif;
    margin-top: 3.7vw;
    padding: 3vw;
    font-size: 3vw;
    height: 2vw;
  }

  article:first-child {
    position: relative;
    width: 100vw;
    margin-top: 4vw;
  }

  article:nth-child(2) {
    display: flex;
    flex-direction: column;
    height: 90vh;
    width: 100%;
  }


  form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: 40vh;
    margin-top: 4vw;

  }

  #contact-title {
    font-family: 'Archivo Black', sans-serif;
    color: rgb(96, 61, 42);
    font-size: 10vh;
  }

  #contact-text {
    font-family: 'Alata', sans-serif;
    font-size: large;
    color: rgb(96, 61, 42);
    width: 50vh;
  }

  button {
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
    letter-spacing: 0.15cm;
  }

  input {
    border: none;
    border-bottom: 0.16vw solid rgb(186, 186, 186);
    outline: none;
    margin-top: 1vw;
    height: 2vw;
  }

  textarea {
    border: none;
    border-bottom: 0.16vw solid rgb(186, 186, 186);
    outline: none;
    margin-top: 2vw;
    height: 3vw;
    resize: none;
  }

  input::placeholder, textarea::placeholder {
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
</style>
  