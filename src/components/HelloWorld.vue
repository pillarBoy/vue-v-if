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
      console.log(this.msg);
    }
  }

}
</script>
