<template>
  <body>
  <header>
    <h1>{{ outputGoal() }}</h1>
  </header>
  <section id="user-goal">
    <h2>{{ myCourseGoal }}</h2>
    <p><a v-bind:href="vueLearnLink">Learn Vue</a></p>
  </section>
  <button id="user-goal" v-on:click="resetInput">My Button</button>
  <input type="text" v-model.lazy="name" placeholder="enter some text">
  <h1>{{ name }}</h1>
  </body>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      courseGoalA: 'Vue Course Goal',
      courseGoalB: 'Fail miserably',
      myCourseGoal: 'My Course Goal',
      vueLearnLink: 'https://vuejs.org/api/built-in-directives.html#v-on',
      vueMessage: 'hello from vue',
      name: ''
    };
  },
  methods: {
    outputGoal: function () {
      const randomNumber = Math.random();
      if (randomNumber < 0.3) {
        return this.courseGoalA;
      } else return this.courseGoalB;
    },
    //v-model replaces the need for this function
    /* setName(event) {
       this.name = event.target.value;
     },*/
    resetInput() {
      this.name = '';
    }
  }
};

</script>

<style>
{
  box-sizing: border-box
;
  }

html {
  font-family: 'Jost', sans-serif;
  }

body {
  margin: 0;
  }

header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #4fc08d;
  color: white;
  text-align: center;
  width: 90%;
  max-width: 40rem;
  }

#user-goal {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
  }

#user-goal h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #4fc08d;
  margin: 0 0 1rem 0;
  }

#user-goal p {
  font-size: 1.25rem;
  font-weight: bold;
  border: 1px solid #4fc08d;
  background-color: #4fc08d;
  color: white;
  padding: 0.5rem;
  border-radius: 25px;
  }

#user-goal input {
  font: inherit;
  border: 1px solid #ccc;
  }

#user-goal input:focus {
  outline: none;
  border-color: #1b995e;
  background-color: #d7fdeb;
  }

#user-goal button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
  }

#user-goal button:hover,
#user-goal button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
  }

</style>
