<template>
<div>
  <component v-bind:is="processedHtml"></component>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'

export default {
  name: "DropdownGaps",
  display: "DropdownGaps",
  components: {},
  props:['content', 'dropdown', 'qid'],
  data() {
    return {
"text":this.content,
"name": 'Q'+this.qid,
    };
  },
  methods: {},
  computed: {

            processedHtml: function () {
let name = this.name;
              function genSelect (name, item, index) {
      let select = '<b-form-select class = "dropdownGap" name = "' + name + '">';
      item.forEach(function(i){
        select = select + '<b-form-select-option value="' + i +'">' +i + '</b-form-select-option>';
        })
        select = select + '</b-form-select>';
        window.console.log(select);
        return select;
        }
  let content = this.text;
  this.dropdown.forEach(function(item, index) {
    let select = genSelect(name, item, index);
    content = content.replace('$$$', select);
    })
    return {template:'<span>'+content+'</span>'}
        }
  }
  }
</script>
<style>
.dropdownGap {
      display: inline-block;
      width: 20%;
      max-height:30px;
      margin-left:5px;
}
</style>