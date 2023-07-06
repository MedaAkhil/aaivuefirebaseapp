<template>
  <center>
    <div>
    <h2>Event Registration</h2>
    <div class="card">
            <span class="card_title">Register</span>
            <p class="card_content">Register and attend the event</p>
            <div class="card_form">
    <form @submit.prevent="register">
      <!-- <label for="name">Name:</label>
      <input type="text" id="name" v-model="name" required>
      <label for="email">Email:</label>
      <input type="email" id="email" v-model="email" required>
      <button type="submit">Register</button> -->
      <input type="text" id="name" v-model="name" placeholder="Enter Student Name"><br>
      <input type="text" id="rollno" v-model="rollno" placeholder="Enter Roll NO"><br>
      <input type="text" id="email" v-model="email" placeholder="Enter Collage Email ID"><br>
      <input type="text" id="branch" v-model="branch" placeholder="Enter Branch"><br>
      <input type="text" id="section" v-model="section" placeholder="Enter Section"><br>
      <input type="text" id="year" v-model="year" placeholder="Enter Year"><br>
      <input type="tel" id="phno" v-model="phno" placeholder="Enter WhatsApp Number"><br>
      <input type="submit">
    </form>
  </div>
        </div>
  </div>
  </center>
</template>

<script>
import { firestore } from '@/firebase'

export default {
  data() {
    return {
      name: '',
      email: '',
      rollno: '',
      branch: '',
      section:'',
      year:'',
      phno:''
    }
  },
  methods: {
    register() {
      console.log("hello");
      firestore.collection('registrations').add({
        name: this.name,
        email: this.email,
        rollno: this.rollno,
        branch: this.branch,
        section:this.branch,
        year:this.year,
        phno:this.phno
      })
      this.name = ''
      this.email = ''
      this.rollno = ''
      this.branch= ''
      this.section=''
      this.year=''
      this.phno=''
    },
  },
  mounted() {
    // Add the first script tag
    const script1 = document.createElement('script');
    script1.src = 'https://unpkg.com/aos@2.3.1/dist/aos.js';
    document.body.appendChild(script1);

    // Add the second script tag
    const script2 = document.createElement('script');
    script2.innerHTML = "AOS.init();"; // Add any additional initialization code if required
    document.body.appendChild(script2);
    AOS.init();
  },
}
</script>


<style>
/* .eventregformsec {
    display: flex;
    flex-direction: row;
    width: 100%;
    height: 100vh;
    align-items: center;
    justify-content: center;
    background-color: white;

}

.formdiv {
    background-color: pink;
    padding: 30px;
    border-radius: 10px;
}

.eventform input {
    font-size: 2rem;
    margin: 1px;
    border: 0 0 1px 0 solid black;
    margin-top: 0;
    padding: 5px;
    border-radius: 10px;
} */
h2{
  margin: 4% 0 2% 0;
}
h2{
  color: white;
}
.eventregformsec {
    width: 100%;
    height: 120vh;
    display: flex;
    align-items: center;
    justify-content: center;
}

.card {
    width: 50%;
    padding: 500px;
    padding: 100px 15px;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 16px;
    background: #12130c;
    border-radius: 20px;
    backdrop-filter: blur(15px);
}

/* .card > *{
    margin: 0;
} */
.card_title {
    font-size: 23px;
    font-weight: 900;
    color: #fff;
}

.card_content {
    font-size: 13px;
    line-height: 18px;
    color: #fff;
}

.card_form {
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 2px;

}

.card_form input {
    /* margin-top: 5px; */
    outline: 0;
    background: rgb(255, 255, 255);
    box-shadow: transparent 0px 0px 0px 1px inset;
    padding: 0.9em;
    border-radius: 14px;
    width: 350px;
    border: 1px solid #333;
    margin: 10px;
    color: black;
}

.card_form button {
    border: 0;
    background: #111;
    color: #fff;
    padding: 0.68em;
    border-radius: 14px;
    font-weight: bold;
}

.sign-up {
    opacity: 0.8;
}

@media (max-width:920px) {
    .card {
        width: 80%;
    }
}

@media (max-width:550px) {
    .card_form input {
        width: 250px;
        padding: 9px;
    }
}

@media (max-width:420px) {
    .card_form input {
        width: 210px;
        padding: 8px;
    }
}

@media (max-width:325px) {
    .card_form input {
        width: 180px;
        padding: 9px;
    }
}
</style>

















