<template>
  <div id="app">
    <!-- <button v-on:click="changeTitle">Change title</button> -->
    <comp-header :title="title" v-on:changeTitleHeader="changeTitle" />
    <form class="form-control" action="">
      <label >Your Name:</label>
      <input type="text" placeholder="Enter your name..." v-model="userName">
      <button v-on:click.prevent="addUser" >Add</button>
    </form>
    <list-user v-on:deleteUser="deleteUser" v-bind:listUser="listUser" />
    <comp-footer :title="title" />
  </div>
</template>

<script>
import CompHeader from "./components/CompHeader.vue";
import CompFooter from "./components/CompFooter.vue";
import ListUser from "./components/ListUser.vue";
export default {
  name: "App",
  data() {
    return {
      title: "This is Title Page",
      userName: '',
      listUser: [
        {
          id: 11,
          title: "Dog Cute",
          avatar: '<img src="https://loremflickr.com/320/240/dog" />',
          active: true,
        },
        {
          id: 12,
          title: "Paris",
          avatar: '<img src="https://loremflickr.com/320/240/paris" />',
          active: true,
        },
        {
          id: 13,
          title: "Brazil",
          avatar: '<img src="https://loremflickr.com/320/240/brazil" />',
          active: true,
        },
        {
          id: 14,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240/rio" />',
          active: true,
        },
        {
          id: 15,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240/girl" />',
          active: true,
        },
        {
          id: 16,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240?random=1" />',
          active: true,
        },
        {
          id: 17,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240?random=2" />',
          active: true,
        },
        {
          id: 18,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240" />',
          active: true,
        },
        {
          id: 19,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240" />',
          active: true,
        },
        {
          id: 110,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240" />',
          active: true,
        },
        {
          id: 111,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240" />',
          active: true,
        },
        {
          id: 112,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240" />',
          active: true,
        },
        {
          id: 113,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240" />',
          active: true,
        },
        {
          id: 114,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240" />',
          active: true,
        },
        {
          id: 115,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240" />',
          active: true,
        },
        {
          id: 116,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240" />',
          active: true,
        },
        {
          id: 117,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240" />',
          active: true,
        },
        {
          id: 118,
          title: "Cat Cute",
          avatar: '<img src="https://loremflickr.com/320/240" />',
          active: true,
        },
      ],
    };
  },
  components: {
    CompHeader,
    CompFooter,
    ListUser,
  },
  methods: {
    changeTitle: function (data) {
      this.title = data;
    },
    deleteUser(data) {     
      this.listUser = this.listUser.filter(u =>{
        return u.id != data.id;
      });
     
    },
    addUser(){
      var data = {
        id : Math.floor(Math.random() * 100),
        title: this.userName,
        avatar: '<img src="https://loremflickr.com/320/240/boy" />',  
        active: true,
      }
      this.listUser.unshift(data);
      this.userName= '';
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.form-control {
  margin: 20px;
  padding: 20px;
}
</style>
