<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <h3>Categories</h3>
    <ul >
      <li v-bind:key="index" v-for="(category, index) in categories" @click="getJoke(category)"  ><a href=#  rel="noopener">{{category}}</a></li>
    </ul>
    <h3>Here's the joke</h3>
    <p>{{joke}}</p>

  </div>
</template>

<script>
export default {
  name: 'ChuckNorris',
  props: {
    msg: String
  },
  data(){
    return  {
      categories: [],
      joke: 'Click category'

    }
  },
  methods: {
    getCategories(){
      let url = 'https://api.chucknorris.io/jokes/categories';

      this.axios.get(url,  {headers: {'Content-Type': 'application/json',
        }}).then((response)=> {
          this.categories=response.data;

    })
  },
    getJoke(command){
    let url='https://api.chucknorris.io/jokes/random?category=' + command ;
      this.axios.get(url,  {headers: {'Content-Type': 'application/json',
        }}).then((response)=> {
        this.joke=response.data.value;

      })
            }
},
created() {
    this.getCategories();
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
