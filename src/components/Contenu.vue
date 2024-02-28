<template>
  <div class="container mt-5">

    <h1 class="text-center">Notre Premier Formulaire</h1>
    <form action="">
      <div class="form-group mt-2">
        <label for="prenom">Ton prénom</label>
        <input v-model.lazy=" formData.prenom" type="text" id="prenom" class="form-control mt-2">
      </div>

      <div class="form-group mt-2">
        <label for="txt">Ton texte</label>
        <textarea v-model.lazy=" formData.txt"  id="txt" class="form-control mt-2"></textarea>
      </div>

      <h3 class="mt-2">Select Box</h3>
      <select v-model="formData.select">
        <option v-bind:key="index" v-for="(pays,index) in formData.listePays">{{ pays }}</option>
      </select>

      <h3 class="mt-2">CheckBox</h3>
      <div class="form-check">
        <input v-model="formData.checkFruits" value="fraise" id="fraise" type="checkbox" class="form-check-input">
        <label for="fraise">Fraise</label>
      </div>

      <div class="form-check">
        <input v-model="formData.checkFruits" value="pomme" id="pomme" type="checkbox" class="form-check-input">
        <label for="pomme">Pomme</label>
      </div>

      <div class="form-check">
        <input v-model="formData.checkFruits" value="cerises" id="cerises" type="checkbox" class="form-check-input">
        <label for="cerises">Cerises</label>
      </div>

      <h2>Résultats</h2>

      <div class="card p-3 mt-2">
        <p>Prénom : {{  formData.prenom }}</p>
        <p style="white-space: pre">Texte : {{  formData.txt }}</p>

        <p>Résultats checkbox</p>
        <ul>
          <li v-bind:key="index" v-for="(fruit,index) in formData.checkFruits">{{ fruit }}</li>
        </ul>

        <p>Choix du select : {{ formData.select }}</p>
      </div>

    </form>
    

  </div>
</template>

<script>

export default {
  name: 'HContenu',
  data: function(){
    return {
      formData: {
        prenom:'',
        txt:'',
        checkFruits: [],
        select: '',
        listePays: ['Cameroun','Russie','Japon','Canada','Mexique']
    }
      }
  },
 methods: {
    
   
 },
 
  components: {
   
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1{
    margin-top: 100px!important;
  }
  .onglets{
    height: 300px;
  }
</style>
