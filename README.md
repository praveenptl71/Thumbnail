# Thumbnail
Thumbnail generator in javascript using base64 of image

``` js
let imgBase64 = "";
let img = new Image();
img.src = imgBase64;
img.onload = ()=> {
      var oc = document.createElement('canvas'), octx = oc.getContext('2d');
      oc.width = img.width;
      oc.height = img.height;
      octx.drawImage(img, 0, 0);
      while (oc.width * 0.5 > width) {
        oc.width *= 0.5;
        oc.height *= 0.5;
        octx.drawImage(oc, 0, 0, oc.width, oc.height);
      }
      oc.width = width;
      oc.height = oc.width * img.height / img.width;
      octx.drawImage(img, 0, 0, oc.width, oc.height);
      let thumb = oc.toDataURL('image/jpeg') ;
      console.log(thumb);
};
img.onerror = (error)=>{
  console.log(error);
}
``` 
