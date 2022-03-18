<template>
  <div style="padding:30px;">
    {{ message }}
    <span :title="message">鼠标悬停几秒钟查看此处动态绑定的提示信息！</span>
    <div id="app-4">
      <p v-if="seen">现在你看到我了</p>
    </div>
    <div id="app-4">
      <ol>
        <li v-for="todo in todos" :key="todo.id">{{ todo.text }}</li>
      </ol>
    </div>

    <button @click="reverseMessage">反转消息</button>
    <input v-model="message">

    <p>Using mustaches: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml" /></p>
  </div>
</template>

<script>

export default {
  name: 'Dashboard',
  data() {
    return {
      message: 'Hello Vue!',
      seen: false,
      todos: [
        { id: 1, text: '学习 JavaScript' },
        { id: 2, text: '学习 Vue' },
        { id: 3, text: '整个牛项目' }
      ],
      rawHtml: 'wewqe'
    }
  },
  computed: {
  },
  created: function() {
    // `this` 指向 vm 实例
    console.log('a is: ' + this.message)
  },
  methods: {
    reverseMessage: function() {
      this.message = this.message.split('').reverse().join('')
    }
  }
}
</script>
