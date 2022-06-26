---
layout: page
title: Generador de Slug
meta_description: 
permalink: /herramientas-seo/generador-de-slug
---

<div class="stripes"></div>
<section class="slug__wrapper">
  <div class="slug__form">
    <!--Title-->
    <h1> Slug URL Generator</h1>
    <!--Form-->
    <label for="text-for-url">Enter text: </label>
    <input type="text" name="text-for-url" id="formText" onkeypress="return searchKeyPress(event);">
    <input type="submit" value="Submit" id="slug__button" onclick="createSlugURL()">
  </div>
  <!--Result-->
  <div class="result">
    <p id="slug-url"></p>
  </div>

</section>


<script>
 function createSlugURL() {
  //Create the URL
  var str = document.getElementById("formText").value;
  var slugStr = str.trim()
    .split(" ")
    .reduce(function(prev, next) {
      return prev.concat([next]);
     // return prev.concat([next.toLowerCase()]); // IN PROGRESS
    }, [])
    .join("-");
  
  //Styling for the 'result' div
  var result = document.querySelector(".result");
  result.classList.add("showResult");
  
   if (str == "") {
     document.getElementById("slug-url").innerHTML = "Please enter text.";
   }
  
 //Display result
  if (str != "") {
    var slugFinal = slugStr.replace("&", "and");
    document.getElementById("slug-url").innerHTML = slugFinal;
  }
}

/*Click button if enter key pressed*/
function searchKeyPress(e) {
  e = e || window.event;
  if (e.keyCode == 13) {
    document.getElementById("slug__button").click();
    return false;
  }
  return true;
}


//Titlecase the string --- IN PROGRESS
String.prototype.toTitleCase = function() {
  var i, j, strTitle, lowers;
  strTitle = this.replace(/([^\W_]+[^\s-]*) */g, function(txt) {
    return txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase();
  });

  // Certain minor words should be left lowercase 
  lowers = ['A', 'An', 'The', 'And', 'But', 'Or', 'For', 'Nor', 'As', 'At', 
  'By', 'For', 'From', 'In', 'Into', 'Near', 'Of', 'On', 'Onto', 'To', 'With', 'Is'];
  for (i = 0, j = lowers.length; i < j; i++) 
    strTitle = strTitle.replace(new RegExp('\\s' + lowers[i] + '\\s', 'g'), 
      function(txt) {
        return txt.toLowerCase();
      });
  return strTitle;
}
</script>



