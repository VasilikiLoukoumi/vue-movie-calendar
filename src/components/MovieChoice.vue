<template>
  <div id="MovieChoice">
   <form @submit.prevent="getMovie()">
   <input type="text" placeholder="enter movie you wish to see" v-model="movie"/>
   </form>
   <ul v-for = "(movie,index) in movies">
   <li><p>{{index+1}}. {{movie.movie}}</p><button id="plusBtn" v-on:click="voteMovie(index)">+</button>
   <button id="minusBtn" v-on:click="downVoteMovie(index)">-</button><p v-bind:id="movie" class="votes">Votes: {{movie.votes}}</p></li>
      
   </ul>
  </div>
</template>

<script>
export default {
  name: 'MovieChoice',
  data: function() {
  return{
  movie: "",
    movies: []
  }
  },
  methods: {
  getMovie: function(){
  this.movies.push({ movie:this.movie,votes:0 });
  this.movie = "";  
  },
  voteMovie: function(index){  
      this.movies[index].votes++;
  },
  downVoteMovie: function(index){ 
      this.movies[index].votes--;
  }
  
  }
}
</script>

<style>
button{
display:inline-block;
padding:4px;
border-radius:8px;
color:dodgerblue;
}
ul{
list-style:none;
}
input{
border-radius:8px;
padding:10px;
}
</style>
