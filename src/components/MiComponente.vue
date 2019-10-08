<template>
  <div class="MiComponente">
    <h1>{{ msg }}</h1>
    <div class="cards-container">
      <div class="card" style="width: 18rem;" v-for="post in posts" v-bind:key="post.key">
        <img :src="post.image" class="card-img-top" alt="...">
        <div class="card-body">
          <div class="card-body-center">
            <h5 class="card-title"><b>{{post.title}}</b></h5>
            <p class="card-text">{{post.content}}</p>
          </div>
          <a :href="post.content" class="btn btn-primary">{{post.linkLabel}}</a>
        </div>
      </div>
    </div>  
  </div>
</template>

<script>
export default {
  name: 'MiComponente',
  props: {
    msg: String,
    
    posts: {
      type: Object,
      default: function () {
        return[
          // title: 'Title',
          // content: 'Place here the content',
          // image:'./assets/logo.png'
          // <h1 v-for="post in posts" v-bind:key="post.key">{{post}}</h1>
        ]
      }
    }
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
/*a {
  color: #42b983;
}*/
.card{
  margin: 32px !important;
}
.card:hover{
  transform: scale(1.2);
  border: 2px solid;
}
.cards-container{
  display: flex;
}
.card-body-center{
  background-color: rgb(250, 247, 247);
  padding: 4px;
  margin: 8px 4px;
}
</style>
