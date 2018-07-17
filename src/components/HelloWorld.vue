<template>
  <div class="hello">
    <p>{{title}}</p>
    <p v-if="show">{{subTitle}}</p>
    <button @click="hideorshow">隐藏</button>
    <div>
      <input type="text" v-model="todo">
      <button @click="handleClick">添加</button>
    </div>
    <ul>
      <li v-for="lists in list" :key='lists'>{{lists}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      title: 'hello',
      subTitle: '看见我',
      show: true,
      todo: '',
      list: ['吃饭', '睡觉', '敲代码']
    }
  },
  methods: {
    handleClick () {
      // this.title = '你好 小程序'
      this.list.push(this.todo)
      this.todo = ''
    },
    hideorshow () {
      this.show = !this.show
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
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
