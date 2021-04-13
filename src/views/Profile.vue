<template>
  <table class="table table-border">
    <thead>
      <tr>
        
        <th scope="col">Prenom</th>
        <th scope="col">Nom</th>
        <th scope="col">Phone</th>
        <th scope="col">CIN</th>
        <th scope="col">Adresse</th>
        <th scope="col">ville</th>
        <th scope="col">Pays</th>
        <th scope="col"> Email</th>
        <th scope="col">Nom Complet</th>
        <th scope="col">CNSS</th>
       
      </tr>
    </thead>
    <tbody>
      <tr>
        
        <td>{{ form1.prenom }}</td>
        <td>{{ form1.nom }}</td>
        <td>{{ form1.telephone }}</td>
        <td>{{ form1.CIN }}</td>
        <td>{{ form1.addresse }}</td>
        <td>{{ form1.ville }}</td>
        <td>{{ form1.pays }}</td>
        <td>{{ form2.email }}</td>
        <td>{{ form2.nomComplet }}</td>
        
        
      </tr>
    </tbody>
  </table>
</template>


<script>
export default {
  data() {
    return {
      form1: {},
      form2: {},
    };
  },
  mounted() {
    this.form1 = JSON.parse(localStorage.getItem("form1"));
    this.form2 = JSON.parse(localStorage.getItem("form2"));
  },
};
</script>