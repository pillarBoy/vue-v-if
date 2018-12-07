# vue-v-if


```
<template>
  <div class="hello">
    <div v-if="msg=='email'">email</div>
    <p v-else>phone</p>
    <button @click="change">change</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'email'
    }
  },
  mounted() {
    setTimeout(() => {
      this.msg = 'email'
    }, 2000)
  },
  methods: {
    change() {
      this.msg = this.msg==='email' ? 'phone' : 'email';
    }
  }

}
</script>
```

```
我是用 vue-cli 创建的项目，在HelloWorld.vue用了上面的代码

正常使用，不会出现问题；
```

##### 问题出现步骤：  


1.运行项目  
2.然后在浏览器中，按鼠标右键，选择 【翻成中文（简体）(T)】  
3.然后点击 change 按钮  

问题出现了，`v-if="msg=='email'"`代码无效了，v-else不会出现  

我看了一下vue 项目源码，找到了processIf 函数，我想定位得更准确的位置。但是我对Vue的源码熟悉度和render过程理解不够深入，所以我找不到根本原因。请问这个问题可以解决吗？如果有解决的可能，请告诉我一下？如果不能解决，也请反馈给我一下这个导致这个问题出现的原因，非常感谢。

希望可以解决这个问题，

实际就是，使用了谷歌翻译之后，v-if 存在一些bug，if条件如果都是数字，不会有问
题，如果是一些单词，那就会被修改掉。
