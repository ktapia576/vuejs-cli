<template>
  <div class="container">
    <ul class="list-group">
      <li 
        class="list-group-item list-group-item-success"
        v-for="user in results"
        :key="user.id.value"
      >
        {{ user.name.first }} {{ user.name.last }} | Email: {{ user.email }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'UserList',
  data() {
    return {
      results: []
    }
  },
  mounted() {
    // Get random users
    axios.get("https://randomuser.me/api/?results=5")
      .then(res => {
        console.log(res)
        this.results = res.data.results
      })
      .catch(err => {
        console.log(err)
      });
  }
}
</script>