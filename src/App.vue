<script>
export default {
  data() {
    return {
      total: "",
    };
  },

  methods: {
    key: function(num) {
      return (this.total += num);
    },
    clear: function() {
      return (this.total = "");
    },
    equal: function() {
      let equal = this.total;
      return (this.total = eval(equal));
    },
    pow: function() {
      return (this.total = this.total ** 2);
    },
    backspace: function() {
      if (this.total.length > 0) {
        this.total = this.total.slice(0, -1);
      }
    },
    recursiveFactorial: function() {
      const num = parseInt(this.total);
      if (isNaN(num)) {
        this.total = "Error";
        return;
      }
      this.total = this.factorial(num).toString();
    },
    factorial: function(n) {
      if (n == 0 || n == 1) {
        return 1;
      } else {
        return n * this.factorial(n - 1);
      }
    },
  },
};
</script>

<template>
    <div id="app">
    <div id="calWrap">
        <div class="top">
            <input type="text" v-model="total" />
        </div>
    <div id="keys">
        <div v-on:click="pow()">x^2</div>
        <div v-on:click="recursiveFactorial()">r!</div>
        <div v-on:click=""></div>
        <div v-on:click="backspace()">~</div>
        <div v-on:click="key(7)">7</div>
        <div v-on:click="key(8)">8</div>
        <div v-on:click="key(9)">9</div>
        <div v-on:click="key('+')">+</div>
        <div v-on:click="key(4)">4</div>
        <div v-on:click="key(5)">5</div>
        <div v-on:click="key(6)">6</div>
        <div v-on:click="key('-')">-</div>
        <div v-on:click="key(1)">1</div>
        <div v-on:click="key(2)">2</div>
        <div v-on:click="key(3)">3</div>
        <div v-on:click="key('*')">*</div>
        <div v-on:click="key(0)">0</div>
        <div v-on:click="clear()" class="clear">c</div>
        <div v-on:click="equal()">=</div>
        <div v-on:click="key('/')">/</div>
    </div>
</div>
</div>
</template>

<style scoped>
body #calWrap {
  background-color: #77889a;
  border-radius: 23px;
  padding: 2em 1em 1em 1em;
  margin: auto;
  width: 292px;
  clear: both;
  display: table;
}
body .top input {
  height: 36px;
  width: 90%;
  font-size: 13px;
  font-weight: bold;
  border-radius: 4px;
  margin: 0 0 14px 0;
  border: 0;
  padding: 0 1em;
  box-shadow: 0px 4px rgba(0, 0, 0, 0.2);
}
body #keys div {
  cursor: pointer;
  width: 66px;
  height: 36px;
  font-weight: bold;
  text-align: center;
  line-height: 2em;
  background: white;
  border-radius: 3px;
  box-shadow: 0px 4px rgba(0, 0, 0, 0.2);
  margin: 0 7px 11px 0;
  float: left;
  transition: all 0.2s ease;
}
body #keys div:hover {
  background-color: #D6D6D6;
}
body #keys .zero {
  width: 138px !important;
}
body #keys .clear {
  background-color: #ffd900 !important;
}

</style>
