<template>

</template>

<script>
import axios from 'axios'

export default {
  name: 'UserList'
}

axios.get("https://randomuser.me/api/?results=5")
  .then(res => {
    console.log(res)
  })
  .catch(err => {
    console.log(err)
  });

</script>