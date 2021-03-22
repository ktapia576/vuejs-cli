<template>
  <ul class="list-group">
    <li 
      class="list-group-item list-group-item-secondary"
      v-for="user in results"
      :key="user.id.value"
    >
      {{ user.name.first }}
    </li>
  </ul>
</template>

<script>
import axios from 'axios'

export default {
  name: 'UserList',
  data() {
    return {
      results: [
        {name: {first: "default"} , id: {value: 127831 }}
      ]
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