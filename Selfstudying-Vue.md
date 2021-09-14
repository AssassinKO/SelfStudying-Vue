2021-09-03

Class and Style Bindings
v-bind is used with class and style.
Binding HTML classes
We can give toggle classes dynamically.
<div v-bind:class="{ active: isActive }"></div> Automatically update.
Using "computed" property.
<div v-bind:class="classObject"></div>
data: {
  isActive: true,
  error: null
},
computed: {
  classObject: function () {
    return {
      active: this.isActive && !this.error,
      'text-danger': this.error && this.error.type === 'fatal'
    }
  }
}
2021-0904
Multiple classes
<div class="static" v-bind:class="{ active: isActive, 'text-danger': hasError }"></div>
data: {
  isActive: true,
  hasError: false
}
Array
<div v-bind:class="[activeClass, errorClass]"></div>

2021-09-06
Conditional rendering.
<h1 v-if="awesome">Vue is awesome!</h1>
<h1 v-else>Oh no 😢</h1>
v-if vs v-for
<h1 v-if="awesome" v-for="OK">Vue is awesome!</h1>
2021-09-13