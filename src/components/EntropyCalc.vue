<template>
    <div>
        <label for="alphabetInput">Input a source alphabet with symbols separated by commas </label>
        <input id="alphabetInput" type="text" v-on:keyup="getAlphabet($event.target.value)"/>
        <label for="messageInput">Input message using your </label>
        <input id="messageInput" type="text" v-on:keyup="calculateEntropy($event.target.value)" v-on:keypress="checkInput($event.key)"/>
    </div>  
</template>

<script>
export default {
  name: 'EntropyCalc',
  props: {
    message: Array,
    entropy: Number
  },
  methods: {
      getAlphabet: function (input) {
          var inputArray = input.split(",");
          var alphabet = Array.from(new Set(inputArray));          
      },
      checkInput: function (key) {
          
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
