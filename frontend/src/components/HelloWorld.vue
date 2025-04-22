<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>{{ messageFromFlask }}</p>

    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      messageFromFlask: ''
    }
  },
  mounted() {
    fetch('http://localhost:5000/api/message')
      .then(res => res.json())
      .then(data => {
        this.messageFromFlask = data.msg
      })
      .catch(err => {
        this.messageFromFlask = 'Error fetching from Flask'
        console.error(err)
      })
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
