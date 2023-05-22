<script>
import CardMain from './components/CardMain.vue';
import CharacterList from './components/CharacterList.vue';
import axios from 'axios';
import {store}  from './store'


export default {
  data() {
    return {
      store,
    }
  },

  components: {
    CardMain,
    CharacterList,
  },

  created() {
    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(response => (this.store.characterList = response.data.data));
  },
};
</script>


<template>
  <div class="title-and-img">
    <img src="./assets/img/Yu-Gi-Oh!_(Logo).jpg" alt="">
    <h1>Yu-Gi-Oh Api</h1>
  </div>
  
  <CardHeader />
  <CardMain />
  <CharacterList />
</template>



<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.title-and-img{
height: 60px;
display: flex;

  h1 {
 margin-left:2rem;
 font-size: 2.5rem;
}

img{
  height: 50px;
}

}




</style>
