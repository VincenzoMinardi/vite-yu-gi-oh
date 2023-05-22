<script>
import CardHeader from './components/CardHeader.vue';
import CardMain from './components/CardMain.vue';
import CharacterList from './components/CharacterList.vue';
import axios from 'axios';
import store from './store';


export default {
  data() {
    return {
      store,
    }
  },

  components: {
    CardHeader,
    CardMain,
    CharacterList,
  },

  created() {
    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
      .then(response => (this.store.characterList = response.data.results));
  },
};
</script>


<template>
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

h1 {
  color: green;
  font-size: 3rem;
}
</style>
