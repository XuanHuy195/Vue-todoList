<template>
  <div class="header">
      <h1 >{{ title }}</h1>
      <button v-on:click="changeTitle">Change title of CompHeader.vue</button>
  </div>
</template>

<script>
export default {
    name: 'comp-header',
    props: {
        title: {
            type: String,
            default: 'Title'
        }
    },
    data() {
        return {
            msg:'This is Header of page'
        }
    },
    methods: {
        changeTitle() {
            var newTitle = "Title did change of CompHeader.vue"
            this.$emit("changeTitleHeader", newTitle);
        }
    }
}
</script>

<style>
.header {
    background-color: red;
    color: white;
}
</style>