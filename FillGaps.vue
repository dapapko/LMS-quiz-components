<template>
  <component v-bind:is="processedHtml"></component>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import LmsGap from "/src/components/LmsGap"
import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'

export default {
  name: "FillGaps",
  display: "FillGaps",
  components: {LmsGap},
  props:['content', 'qid'],
  data() {
    return {
      name:this.qid,
    };
  },
  methods: {},
  computed: {

            processedHtml () {
                let html = this.content.replaceAll('###', '<b-form-input type="text" size="sm" :name="name" style="display:inline-block; width:25%"></b-form-input>').replaceAll('@@@', '<lms-gap></lms-gap>');
                return {
                    template: '<div>' + html + '</div>',
                    props: {
                name: {
                    type: null,
                    default: () => { return this.name }
                }
                }

            }
        }
  }
  }
</script>
<style scoped></style>