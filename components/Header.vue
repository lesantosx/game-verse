<template>
  <header class="flex justify-between items-center">    
    <div class="flex">
      <h1 class="title-header">GameVerse</h1>
      <div class="items-center flex">
        <input type="text" class="search-input" placeholder="Search..." />
      </div>      
    </div>
    <div class="flex align-middle actions-btn">
      <Icon name="i-heroicons-heart-solid" size="1.7em" class="hover:scale-110" />
      <Icon name="i-heroicons-shopping-cart-solid" size="1.7em" class="hover:scale-110" />
      <Icon 
        v-if="isDarkMode"
        name="i-heroicons-moon"
        size="1.7em"
        class="hover:scale-110"
        @click="$colorMode.preference = 'light'" 
      />
      <Icon
        v-else
        name="i-heroicons-sun"
        size="1.7em"
        class="hover:scale-110"
        @click="$colorMode.preference = 'dark'"
      />
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {}
  },
  computed: {
    isDarkMode() {
      return this.$colorMode.preference === 'dark'
    }
  }
}

</script>

<style>
body {
  background-color: #fff;
  color: rgba(0,0,0,0.8);
}
.dark-mode body {
  background-color: #1F1C28;
  color: #ebf4f1;
}
.light-mode body {
  background-color: white;
  color: #334155;
}

.title-header {
  font-size: 28px;
  font-weight: 700;
  margin-right: 100px;
  cursor: pointer;
}
.search-input {  
  display: block;
  width: 350px;
  height: 33px;
  padding: 10px 45px;
  color: white;  
  font-size: 16px;
  border: none;
  border-radius: 7px;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px,
    rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
}

.search-input:focus {
  outline: none;
}
.dark-mode .search-input {
  background: rgba(217, 217, 217, 0.4) url("assets/search-icon.svg") no-repeat 18px center;
  background-size: 18px 18px;
}
.light-mode .search-input {
  background: #334155 url("assets/search-icon.svg") no-repeat 18px center;
  background-size: 18px 18px;
}

.actions-btn{
  svg {
    margin-right: 15px;
    cursor: pointer;
  }

  svg:hover {
    color: #8b5cf6;
  }
}

</style>