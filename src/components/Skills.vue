<template>
  <div class="hello">
    {{ name }}
    {{ btnState ? 'The button is disabled' : 'The button is active'}}
    <button class="button is-primary" v-on:click="changeName" v-bind:disabled="btnState">Change name</button>
    <!-- <button class="button is-primary" v-bind:class="{'is-loading' : bgColor}" v-on:click="changeName">Change name</button> -->
    <div class="holder">
      <ul>
        <li v-for="(data, index) in skills" :key='index'>{{ data.skill }}</li>
      </ul>
      <p v-if="skills.length >=1">You have more than 1 skills</p>
      <p v-else>You have less skills.</p>
      <!-- <div v-bind:class="{ alert: showAlert, 'another-class' : showClass}"></div>  -->
      <div v-bind:class="alertObject"></div> 
      <div v-bind:style="{backgroundColor: bgColor, width: bgWidth, height: bgHeight}"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      // name: 'Coursetro',
      // btnState: true,
      skills: [
        {"skill" :"Vue.js"},
        {"skill" :"Frontend dev"}
      ],
      alertObject: {
        alert: true,
        "another-class": true
      },

      bgColor: 'yellow',
      bgWidth: '100%',
      bgHeight: '30px'
      // showAlert: true,
      // showClass: true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .alert {
    background-color: yellow;
    width :100%;
    height: 30px;
  }

  .another-class {
    border: 1px solid black;
  }
</style>
