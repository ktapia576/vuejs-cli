<template>
    <li 
        class="list-group-item list-group-item-success"
        v-for="user in users"
        :key="user.id.value"
    >
        {{ user.name.first }} {{ user.name.last }} | Email: {{ user.email }}
    </li>
</template>

<script>
export default {
    name: 'UserListUser',
    props: {
        users: Array,
    }
}
</script>