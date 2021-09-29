Self-Studying:   Vue.js (3)
--2021-09-22--
Mustaches cannot be used inside HTML attributes. Instead, use a v-bind directive.
Mustaches: id, class, disabled, name, href, click, etc
v-bind:id="", v-bind:class="", v-bind:name=""
v-bind:[attributeName] = "url"
v-on[eventName]="dosomething"    ==    v-on:focus = "dosomething" (eventName="focus")
v-on:submit.prevent="onSubmit"    =>       event.preventDefault()
:href="", :id="", :[key]="" (v-bind)
@click="dosomething", @[key]="dosomething"  (v-on)
--2021-09-24--
Data Properties
const app = Vue.createApp({
  data() {
    return { count: 4 }
  }
})

vm.count = 5
--2021-09-27--
Class and Style Binding.
<div
  class="static"
  :class="{ active: isActive, 'text-danger': hasError }"
></div>
<div :class="[isActive ? activeClass : '', errorClass]"></div>

<div :style="styleObject"></div>
data() {
  return {
    styleObject: {
      color: 'red',
      fontSize: '13px'
    }
  }
}
Contitional Rendering
<h1 v-if="awesome">Vue is awesome!</h1>
<h1 v-else>Oh no</h1>

<h1 v-show="ok">Hello!</h1>
The difference is that an element with v-show will always be rendered and remain in the DOM; v-show only toggles the display CSS property of the element.

List Rendering
<ul id="array-rendering">
  <li v-for="item in items">
    {{ item.message }}
  </li>
</ul>
Vue.createApp({
  data() {
    return {
      items: [{ message: 'Foo' }, { message: 'Bar' }]
    }
  }
}).mount('#array-rendering')

<ul id="array-with-index">
  <li v-for="(item, index) in items">
    {{ parentMessage }} - {{ index }} - {{ item.message }}
  </li>
</ul>
Vue.createApp({
  data() {
    return {
      parentMessage: 'Parent',
      items: [{ message: 'Foo' }, { message: 'Bar' }]
    }
  }
}).mount('#array-with-index')

Array Detection
push()
pop()
shift()
unshift()
splice()
sort()
reverse()

<ul v-for="numbers in sets">
  <li v-for="n in even(numbers)" :key="n">{{ n }}</li>
</ul>
data() {
  return {
    sets: [[ 1, 2, 3, 4, 5 ], [6, 7, 8, 9, 10]]
  }
},
methods: {
  even(numbers) {
    return numbers.filter(number => number % 2 === 0)
  }
}
v-for with v-if
<li v-for="todo in todos" v-if="!todo.isComplete">
  {{ todo.name }}
</li>

<template v-for="todo in todos" :key="todo.name">
  <li v-if="!todo.isComplete">
    {{ todo.name }}
  </li>
</template>
--2021-09-28--
Event Handling
Form Input Bindings
<div id="v-model-select-dynamic" class="demo">
  <select v-model="selected">
    <option v-for="option in options" :value="option.value">
      {{ option.text }}
    </option>
  </select>
  <span>Selected: {{ selected }}</span>
</div>
Vue.createApp({
  data() {
    return {
      selected: 'A',
      options: [
        { text: 'One', value: 'A' },
        { text: 'Two', value: 'B' },
        { text: 'Three', value: 'C' }
      ]
    }
  }
}).mount('#v-model-select-dynamic')
--2021-09-29--
Props in Vue.js
