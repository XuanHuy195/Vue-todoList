<template>
  <div class="footer">
      <h1>{{ title }}</h1>
  </div>
</template>

<script>
export default {
    name: 'comp-footer',
    props: {
        title: {
            type: String,
            default: 'Title'
        }
    },
    data() {
        return {
            msg: 'This is Footer of page',
        }
    }
}
</script>

<style>
.footer {
    background-color: blue;
    color: white;
}
</style>