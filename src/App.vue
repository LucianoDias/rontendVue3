<template>
  <div class="container-fluid ">
    <div class="card pt-4 pb-2" v-for="user in users" :key="user.id">
      <div class="card-body" >
        {{ user.name }}
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      users: []
    }
  },
  mounted() {
    fetch("http://127.0.0.1:8000/api/users/")
         .then(response => response.json())
         .then((res) => {
            this.users = res.data;
         })
  },
  components: {
   
  }
}
</script>

<style>

</style>
