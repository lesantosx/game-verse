<template>
  <div id="sidebar">
    <template v-for="route in routesLink">
      <NuxtLink :to="route.route" class="items-center hover:text-white" active-class="active">
        <Icon :name="route.icon" size="1em" />
        <h1>{{ route.name }}</h1>
      </NuxtLink>
    </template>
  </div>
</template>

<script>
export default {
  data() {
    return {
      routesLink: [
        { name: "Store", icon:"i-heroicons-building-storefront-20-solid", route: "/" },
        { name: "Library", icon:"i-heroicons-squares-2x2-20-solid", route: "/library" },
        { name: "Community", icon:"i-heroicons-user-group-solid", route: "/community" }
      ]
    }
  }
}
</script>

<style>
#sidebar{
  svg {
    margin-right: 15px;
  }
  a {
    width: 180px;
    height: 50px;
    display: flex;
    text-decoration: none;    
    font-size: 20px;
    font-family: "Aleo", serif;;
    padding: 15px;
    margin-bottom: 8px;
    border-radius: 12px;
  }
  a:hover {
    background-color: #3D2F5A;
  }
  .active {
    color: white;
    background-color: #3D2F5A;
  }
}
</style>