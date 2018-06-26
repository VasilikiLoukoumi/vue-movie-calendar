<template>
  <div id="MovieChoice">
   <form @submit.prevent="getMovie">
   <input type="text" placeholder="enter movie you wish to see" v-model="movie"/>
   </form>
   <ul v-for = "(movie,index) in movies">
   <li><p>{{index+1}}. {{movie}}</p><button id="plusBtn" v-on:click="voteMovie">+</button>
   <button id="minusBtn" v-on:click="downVoteMovie">-</button><p v-bind:id="movie" class="votes">Votes: 0</p></li>
      
   </ul>
  </div>
</template>

<script>
export default {
  name: 'MovieChoice',
  data: function() {
  return{
  movie: "",
  movies:[],
  votes:0,
  isActive:false,
  movieId:""
  }
  },
  methods: {
  getMovie: function(){
  this.movies.push(this.movie);
  this.movieId = this.movie;
  this.movie = "";
  this.votes = 0;
  this.isActive = true;  
  },
  voteMovie: function(){  
  if(this.isActive){
  this.votes++;
  this.isActive = false;
  document.getElementById(this.movieId).innerHTML = "Votes: "+ this.votes;
  }  
  },
  downVoteMovie: function(){ 
  if(this.isActive){
  this.votes--;
  this.isActive = false; 
  document.getElementById(this.movieId).innerHTML = "Votes: "+ this.votes;
  }
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
