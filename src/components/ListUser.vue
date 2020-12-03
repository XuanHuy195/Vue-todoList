<template>
  <div class="list-user">
    <user v-for="item in listUser" v-bind:key="item.id" v-bind:user="item" v-on:deleteUser="deleteUser"/>
  </div>
</template>

<script>
import User from './User.vue'
export default {
    name: 'list-user',
    data() {
        return {

        }
    },
    components: {
        User
    },
    props: {
        listUser: {
            type: Array,
            default: () => {
                return []
            },
        }
    },
    methods: {
        deleteUser(data) {
            this.$emit('deleteUser', data);
        }
    }
}
</script>

<style>
.list-user {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}
</style>