<template>
  <div class="hello">
    <h4>input decimal</h4> <br><br>
    <input type="number" v-model="dec" @keydown.enter.prevent="cal()"/>
    <button @click="cal()">ok</button> <br><br>
    <br><br><br>
    <h1>{{bin}}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      dec: '',
      bin: ''
    }
  },
  methods: {
    cal () {
      let n = 1
      this.bin = ''
      let m, i
      for (i = this.dec; i > 0; i = i / 2) {
        i = Math.floor(i)
        m = i % 2
        this.bin = +this.bin + (m * n)
        n = n * 10
      }
      // console.log(this.dec, this.bin)
      this.dec = ''
    }
    // cal () {
    //   let bit = ''
    //   while (this.dec > 0) {
    //     bit = (this.dec % 2) & +bit
    //     console.log(bit)
    //     this.dec = this.dec / 2
    //     this.dec = Math.floor(this.dec)
    //   }
    //   this.bin = bit
    // }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
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
