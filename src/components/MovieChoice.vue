<template>
  <div id="MovieChoice">
   <form @submit.prevent="getMovie()">
   <input type="text" placeholder="enter movie you wish to see" v-model="movie" v-validate="{ required: true, min:1 , max:50  }" name = "movie" />
   </form>
   <ul v-for = "(movie,index) in movies">
       <li>
           <p>{{index+1}}. {{movie.movie.toUpperCase()}}</p>
           <button id="plusBtn" v-on:click="voteMovie(index)">👍</button>
           <button id="minusBtn" v-on:click="downVoteMovie(index)">👎</button>
           <p v-bind:id="movie" class="votes">Votes: {{movie.votes}}</p>
       </li>
      
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
      getMovie: function () {
          this.$validator.validateAll().then((result) => {
              if (result) {
                  this.movies.push({ movie: this.movie, votes: 0 });
                  this.movie = "";
              }
              else {                  
                  swal({
                      title: this.$validator.errors.first('movie'),
                      icon: "warning",
                      button: "I undestand."
                  });
              }

          });
              
         
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

<style scoped> 
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
li {
background-color: white;
border-radius: 8px;
}

</style>
