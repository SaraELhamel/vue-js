
<style scoped>
body {
  font-family: "Montserrat", sans-serif;
  font-weight: normal;
  width: 100vw;
  height: 100vh;
  background-color: #233952;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.input-container {
  width: 100%;
  max-width: 372px;
}

.form {
  position: relative;
  margin-bottom: 40px;
  height: 25px;
}
.form input {
  font-family: "Montserrat", sans-serif;
  font-weight: normal;
  outline: none;
  background-color: transparent;
  padding: 0 0 0px 0;
  border: none;
  text-rendering: auto;
  color: white;
  font-size: 14px;
  display: inline-block;
  text-align: start;
  margin: 0em;
  transition: 0.2s ease-out;
  width: 100%;
}
.form input:focus {
  color: #c4a773;
}
.form input:focus ~ .label, .form input:valid ~ .label {
  transform: translateY(-20px);
  font-size: 12px;
  color: rgba(255, 255, 255, 0.3);
}
.form input:focus ~ .t-line {
  width: 100%;
}
.form .label {
  color: white;
  font-size: 14px;
  position: absolute;
  top: 0;
  left: 0;
  transition: 0.2s ease-in-out;
  user-select: none;
  pointer-events: none;
}
.form .line {
  position: absolute;
  bottom: 0;
  background: rgba(255, 255, 255, 0.3);
  height: 1px;
  width: 100%;
}
.form .t-line {
  position: absolute;
  bottom: 0;
  width: 0%;
  height: 1px;
  background: #c4a773;
  transition: 0.2s ease-in-out;
}

.form-long {
  position: relative;
  margin-bottom: 40px;
}
.form-long textarea {
  font-family: "Montserrat", sans-serif;
  font-weight: normal;
  color: white;
  width: 100%;
  height: 80px;
  border: none;
  overflow: auto;
  outline: none;
  background: none;
  resize: none;
}
.form-long textarea:focus {
  color: #c4a773;
}
.form-long textarea:focus ~ .label {
  transform: translateY(-20px);
  color: rgba(255, 255, 255, 0.3);
  font-size: 12px;
}
.form-long textarea:focus ~ .t-line {
  width: 100%;
}
.form-long .label {
  font-size: 14px;
  color: white;
  position: absolute;
  top: 0;
  left: 0;
  user-select: none;
  pointer-events: none;
  transition: 0.2s ease-in-out;
}
.form-long .line {
  position: absolute;
  bottom: 0;
  background: rgba(255, 255, 255, 0.3);
  height: 1px;
  width: 100%;
}
.form-long .t-line {
  position: absolute;
  bottom: 0;
  background: #c4a773;
  height: 1px;
  width: 0%;
  transition: 0.2s ease-in-out;
}

.wrapper-secondary-btn .secondary-btn {
  font-family: "Montserrat", sans-serif;
  font-weight: bold;
  font-size: 14px;
  border: 1px solid rgba(207, 179, 128, 0.3);
  background-color: transparent;
  cursor: pointer;
  color: #dcc08e;
  padding: 10px 20px;
  transition: all 0.2s ease-out;
}
.wrapper-secondary-btn .secondary-btn:hover {
  border: 1px solid #cfb380;
}
.wrapper-secondary-btn .secondary-btn:active {
  color: #c4a773;
  border: 1px solid #c4a773;
}
.input-container{
  background-color:grey;
  margin-top:2%;
  Margin-left:28%;
  padding:150PX;
}
</style>
<template>
<h2>Personnel Info form</h2>
<form class="input-container" @submit.prevent="handelSubmit">
  <div class="form">
    <input type="text" required
    id="prenom"
    v-model="form1.prenom"
    >
    <div class="label">Prenom</div>
    <div class="line"></div>
    <div class="t-line"></div>
  </div>
  <div class="form">
    <input type="text" required
     id="nom"
    v-model="form1.nom"
    >
    <div class="label">Nom</div>
    <div class="line"></div>
    <div class="t-line"></div>
  </div>
  <div class="form">
    <input type="number" required
     id="telephone"
    v-model="form1.telephone"
    >
    <div class="label">Tel.</div>
    <div class="line"></div>
    <div class="t-line"></div>
  </div>
  <div class="form">
    <input type="number" required
     id="CIN"
    v-model="form1.CIN"
    >
    <div class="label">CIN</div>
    <div class="line"></div>
    <div class="t-line"></div>
  </div>
   <div class="form">
    <input type="number" required
     id="passport"
    v-model="form1.passport"
    >
    <div class="label">Passport</div>
    <div class="line"></div>
    <div class="t-line"></div>
  </div>
  <div class="form">
    <input type="text" required
     id="adresse"
    v-model="form1.adresse"
    >
    <div class="label">Adresse</div>
    <div class="line"></div>
    <div class="t-line"></div>
  </div>
  <div class="form">
    <input type="text" required
     id="ville"
    v-model="form1.ville"
    >
    <div class="label">Ville</div>
    <div class="line"></div>
    <div class="t-line"></div>
  </div>
  <div class="form">
    <input type="text" required
     id="pays"
    v-model="form1.pays"
    >
    <div class="label">Pays</div>
    <div class="line"></div>
    <div class="t-line"></div>
  </div>
  
  <div class="wrapper-secondary-btn">
    <button  type= submit class="secondary-btn">Send</button>
  </div>
</form>
  
</template>

<script>
export default {
  name: "PersInfo",
  data() {
    return {

      form1: {

      prenom: "",
      nom: "",
      telephone: "",
      CIN: "",
      passport: "",
      addresse: "",
      ville: "",
      pays: "",

      }

     
    };
  },
  methods : {
    handelSubmit(){
       localStorage.setItem('form1',JSON.stringify(this.form1));
       redirect('/ProInfo')
    }
  }
};
</script>
