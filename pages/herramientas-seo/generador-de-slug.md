---
layout: page
title: Generador de Slug
meta_description: 
permalink: /herramientas-seo/generador-de-slug
---
{::options parse_block_html="true" /}
{::options parse_span_html="true" /}
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.1.10/vue.min.js"/>
<div id="app" class="container">
  <div class="row">
    <div class="col-md-6 offset-md-3">
      <h3>Vue.js 2 slug generator</h3>
      
      <hr />

      <div class="form-group">
        <label>Input:</label>
        <input type="text" class="form-control" v-model="input" placeholder="Enter your title"/>
      </div>

      <div class="form-group">
        <label>Slug:</label>
        &lt;input :value=&quot;slug&quot; type=&quot;text&quot; class=&quot;form-control&quot; disabled&gt;
      </div>
  </div>
  </div>
</div>



<script>
  const app = new Vue({
  el: '#app',
  
  data: {
    input: 'Thís is a côol & awësome title !'
  },
  
  computed: {
    slug: function () {
      return this.slugify(this.input)
    }
  },
  
  methods: {

    slugify (text, ampersand = 'and') {
      const a = 'àáäâèéëêìíïîòóöôùúüûñçßÿỳýœæŕśńṕẃǵǹḿǘẍźḧ'
      const b = 'aaaaeeeeiiiioooouuuuncsyyyoarsnpwgnmuxzh'
      const p = new RegExp(a.split('').join('|'), 'g')

      return text.toString().toLowerCase()
        .replace(/[\s_]+/g, '-')
        .replace(p, c =>
          b.charAt(a.indexOf(c)))
        .replace(/&/g, `-${ampersand}-`)
        .replace(/[^\w-]+/g, '')
        .replace(/--+/g, '-')
        .replace(/^-+|-+$/g, '')
    }   
  }
})
</script>



