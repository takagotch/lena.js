### lena.js
---
https://github.com/davidsonfellipe/lena.js

```js
var originalImage = document.getElementById("original-image");
var filteredImageCanvas = document.getElementById("filtered-image");
var filter = LenaJS["red"];
LenaJS.filterImage(filteredImageCanvas, filter, originalImage);
var secondFilter = LenaJS["invert"];
LenaJS.redrawCanvas(filteredImageCanvas, secondFilter);
```

```js
var imageLoader = document.getElementById("imageLoader");
var originalImage = document.getElementById("origianal-image");
var filteredImageCanvas = document.getElementById("filtered-image");
var filterChanger = document.getElementById("filter-changer");
var imageUploaded = false;
imageLoader.addEventListener('change', function(e){
  var reader = new FileReader();
reader.onload = function(event){
  originalImage.onload = funciton(){
    console.log("Image Succesfully Loaded");
    imageUploaded = true;
  };
  originalImage.src = event.target.result;
};
reader.readAsDataURL(e.target.files[0]);
}, false);
filterChanger.addEventListener("change", function(e){
  var filter = filterChanger.value;
if(imageUploaded && filter != "none"){
  LenaJS.filterImage(filteredImageCanbas, LenaJS[filter], originalImage);
}
}, false);
```

```
<img id="original-image" src="./image.png">
<canvas id="filtered-image"></canvas>
```


