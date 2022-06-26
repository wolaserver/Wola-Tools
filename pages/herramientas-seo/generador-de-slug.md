---
layout: page
title: Generador de Slug
meta_description: 
permalink: /herramientas-seo/generador-de-slug
---

<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/1.0.22/vue.min.js"></script>

<div id="post">
  <input v-model="title" type="text" id="title" name="title" placeholder="Enter post title"/>
  <p id="slug"><span>"{{ slug }}"</span></p>
</div>



<script>
 new Vue({
  el: '#post',
  data: {
    title: "Slug",
  },
  computed: {
    slug: function() {
      var slug = this.sanitizeTitle(this.title);
      return slug;
    }
  },
  methods: {
    sanitizeTitle: function(title) {
      var slug = "";
      // Change to lower case
      var titleLower = title.toLowerCase();
      // Letter "e"
      slug = titleLower.replace(/e|é|è|ẽ|ẻ|ẹ|ê|ế|ề|ễ|ể|ệ/gi, 'e');
      // Letter "a"
      slug = slug.replace(/a|á|à|ã|ả|ạ|ă|ắ|ằ|ẵ|ẳ|ặ|â|ấ|ầ|ẫ|ẩ|ậ/gi, 'a');
      // Letter "o"
      slug = slug.replace(/o|ó|ò|õ|ỏ|ọ|ô|ố|ồ|ỗ|ổ|ộ|ơ|ớ|ờ|ỡ|ở|ợ/gi, 'o');
      // Letter "u"
      slug = slug.replace(/u|ú|ù|ũ|ủ|ụ|ư|ứ|ừ|ữ|ử|ự/gi, 'u');
      // Letter "d"
      slug = slug.replace(/đ/gi, 'd');
      // Trim the last whitespace
      slug = slug.replace(/\s*$/g, '');
      // Change whitespace to "-"
      slug = slug.replace(/\s+/g, '-');
      
      return slug;
    }
  }
});
</script>



