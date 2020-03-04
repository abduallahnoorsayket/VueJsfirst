<template>
  <div id="app">
    <br>
    <br>
    <br>
    <br>
    
    <h1>{{tittle}} </h1>
    <Navbar />
    <AllFriends :friends ="friends" @delete="deleteFriend"/>
    <OnlineFriends :friends ="friends" />



   
    
    
  </div>
  
</template>

<script>
import Navbar from './Navbar'
import AllFriends from './AllFriends'
import OnlineFriends from './OnlineFriends'

export default { 
  name: 'app',
  components:{
    Navbar,
    OnlineFriends,
    AllFriends
   } ,  
  data () {
    return {
     tittle :'  abdullah noor   first vue appp',
      friends:[
                {name:'Mario',online:true},
                {name:'jhon',online:false},
                {name:'sayket',online:true},
                {name:'kevin',online:false}  
            ]
     
    
  }
  },
  methods:{
    deleteFriend(payload){
      console.log(payload)
      this.friends= this.friends.filter(friend => {
        return friend.name !== payload.name
      })
    }

  }  

}
</script>

  
<style>
h1{
  color: #444;
  font-weight: normal;
  text-align: center;
  }
</style>
