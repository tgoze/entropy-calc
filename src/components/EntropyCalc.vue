<template>
    <div>
        <label for="alphabetInput">Input a source alphabet with symbols separated by commas </label>
        <input id="alphabetInput" type="text"/>
        <br/>
        <label for="messageInput">Input message using your </label>
        <input id="messageInput" type="text" v-on:keypress="calculateEntropy($event)"/>
        <br/>
        <h5>{{entropy}}</h5>
    </div>  
</template>

<script>
export default {
  name: 'EntropyCalc',
  props: {    
    entropy: 0        
  },
  methods: {      
      calculateEntropy: function (event) {
        var alphabetEl = document.getElementById("alphabetInput");
        var alphabet = Array.from(new Set(alphabetEl.value.split(",")));  
        var messageEl = document.getElementById("messageInput");
        var message = messageEl.value;
        if (alphabet.includes(event.key)) {
            var probability = ((message.match(new RegExp(event.key, "g")) || []).length + 1) / message.length;
            this.entropy += -probability * Math.log2(probability);
        }
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
