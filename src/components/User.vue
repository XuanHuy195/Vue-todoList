<template>
  <div class="card">
    <h3>{{ user.title }}</h3>
     <div v-html="user.avatar"></div>
     <button class="deleteBtn" v-on:click="deleteUser">Delete</button>
  </div>
</template>

<script>
export default {
    name: 'user',
    data() {
        return {
            
        }
    },
    props: {
        user: {
            type: Object,
            default: null
        }
    },
    methods: {
        deleteUser() {
            var data = {
                id: this.user.id
            }
            this.$emit('deleteUser',data);
        }
    }
}
</script>

<style>
 .card {
     padding: 10px;
     margin: 10px;
     width: 350px;
     height: 300px;
     border: 1px solid black;
     position: relative;
 }
 .deleteBtn {
     position: absolute;
     top: 0;
     right: 0;
 }
</style>