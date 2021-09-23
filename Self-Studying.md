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