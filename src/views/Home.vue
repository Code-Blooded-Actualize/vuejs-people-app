<template>
  <div class="home">
    <h1>Interesting People</h1>

    <div>
      Name: <input v-model="newPerson.name">  
      Bio: <input v-model="newPerson.bio">
      <button v-on:click="addPerson()">Add Person</button>
    </div>

    <div>
      <h4>Total Number of People: {{ people.length }}</h4>
    </div>

    <div v-for="person in people">
      <h2 @click="toggleBio(person)">{{ person.name }}</h2>
      <h3 v-if="person.bioVisible">{{ person.bio }}</h3>
      <button @click="deletePerson(person)">Delete</button>
    </div>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      people: [
        {
          name: "Bob",
          bio: "Small batch salvia Marfa chillwave delectus, odio forage art party laborum street art minim fixie locavore hoodie mollit.",
          bioVisible: true
        },
        {
          name: "Alice",
          bio: "Tattooed letterpress gluten-free ugh, adipisicing scenester church-key gentrify tousled gastropub pour-over Shoreditch asymmetrical lomo High Life.",
          bioVisible: true
        },
        {
          name: "Tibor",
          bio: "Incididunt photo booth ethical reprehenderit adipisicing. Echo Park readymade Bushwick distillery Tonx. +1 semiotics qui duis literally.",
          bioVisible: true
        },
        {
          name: "Živa",
          bio: "Excepteur shabby chic semiotics Marfa, quinoa try-hard polaroid pariatur banh mi selfies incididunt brunch trust fund. Ethical dolor PBR&B Tumblr.",
          bioVisible: true
        }
      ],
      newPerson: {name: "", bio: "", bioVisible: true}
    };
  },
  created: function() {},
  methods: {
    toggleBio: function(inputPerson) {
      inputPerson.bioVisible = !inputPerson.bioVisible;
    },
    addPerson: function() {
      if (this.newPerson.name && this.newPerson.bio) {
        this.people.push(this.newPerson);
        this.newPerson = {name: "", bio: "", bioVisible: true};
      }
    },
    deletePerson: function(inputPerson) {
      var index = this.people.indexOf(inputPerson);
      this.people.splice(index, 1);
    }
  },
  computed: {}
};
</script>



















