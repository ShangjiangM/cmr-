<template>
  <div id="app">
    <div>{{message}}</div>
    <button @click='changeText'>改变一下我把</button><br>
    <input type="text" v-model="a">
    <div>{{a}}</div>
    <div>{{c+1}}</div>
    <hr>
    <div>{{fullName}}</div>
    <div v-for="(item,key) in list">{{item}}-----{{key}}</div>
    <div v-for='(item,key) in list1'>{{item}}-----{{key}}</div>
    <div v-if='!flag'>dadada</div>
    <button @click='ab()'>再试试</button>
    你好啊啊啊
    <div></div>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data() {
      return {
        message: 'Hello,the man is ku',
        a: 'dadhahdh ',
        list: [111111, 2222222, 3333333],
        flag: true,
        list1: {
          'a': '1111111',
          'b': '2222222',
        },
        c: 1,
        firstName: 'Foo',
        lastName: 'Bar',
      }

    },
    component: {

    },
    computed: {
      fullName: {
        // getter
        get: function () {
          return this.firstName + ' ' + this.lastName
        },
        // setter
        set: function (newValue) {
          var names = newValue.split(' ')
          this.firstName = names[0]
          this.lastName = names[names.length - 1]
        }
      }
    },
    methods: {
      ab() {
        console.log('nihaoa')
      },
      changeText() {
		this.message = this.message.split('').reverse().join('')
      }
    },
    beforeCreate() {
      console.log('页面已经被创建之前。。。。。。')
    },
    created() {
      console.log('页面已经被创建')
    },
    beforeMount() {
      console.log('页面正在被mounted之前。。。。。')
    },
    mounted() {
      console.log('页面已经被mounted了')
    },
  }

</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

</style>
