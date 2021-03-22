<template>
  <div class="container">
    <ul class="list-group">
      <UserListUser :users="results"/>
    </ul>
  </div>
</template>

<script>
import UserListUser from './UserListUser.vue'
import axios from 'axios'

export default {
  name: 'UserList',
  components: {
    UserListUser
  },
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