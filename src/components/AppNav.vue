<script>
import AppSelect from './AppSelect.vue';


export default {

    name: 'AppNav',

    components : {
        AppSelect,
    }

  
  }

</script>

<template>

<nav>
    <div class="text-nav">
        <h1>Yu-Gi-Oh Api</h1>
        
    </div>
</nav>
  
</template>

<style lang="scss">

nav{
    background-color: #fff;
    color: black;

    padding: 10px;
}

.text-nav{
    display: flex;
    justify-content: space-between;
}

</style>