<script>
</script>

<template>
   <div class="big-container">
        <select name="level" id="">
            <option class="easy" value="esasy">Alien</option>
        </select>
        <div class="small-container">
            <div class="bar-black">
                <h3>Found 39 Card</h3>
            </div>
            <div v-for="character in store.characterList" class="card-container"
            :key="character.id">

            </div>
        </div>
    </div>
   
</template>


<style lang="scss" scoped>
.big-container{
    background-color:rgb(212, 143, 56);
    height: 100vh;
    width: 100%;
    select{
        font-size: 1.5rem;
        margin: 3rem;
        height: 35px;
        width: 200px;
       }
}

.small-container{
    max-width: 1000px;
    background-color: white;
    margin: auto;
   height: 85%;
   .bar-black{ 
    background-color: black;
    height: 60px;
    h3{
        color: white;
        align-content: center;
    }
}

.card-container{
    display: flex;
    flex-wrap: wrap;
}

}
</style>