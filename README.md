# Tarfile.js

 A JavaScript library to load local and remote tar files from tar archives and json_packed files

 TarFile - A JavaScript library to load multiple files from 
 tar archives and json_packed files (see https://gist.github.com/kig/408333)

### Example 1: Loading multiple files from a local file

```
 TarFile.load_file(file, function(tf){
    this.files.forEach(function(f) {
        // Do something clever with the file
        console.log(f);
    });
 });
```

### Example 2: Loading multiple images from a tarball.

```
 TarFile.load('images.tar', function(xhr) {
     this.files.forEach(function(f) {
         var e = document.createElement('div');
         document.body.appendChild(e);
         var p = document.createElement('p');
         p.appendChild(document.createTextNode(f.filename + " (" + f.length + " bytes)"));
         e.appendChild(p);
         var img = new Image();
         img.src = f.toDataURL();
         e.appendChild(img);
     });
 });
```

### Example 3: Streaming images from a tarball.

```
 TarFile.stream('images.tar', function(f) {
     var e = document.createElement('div');
     document.body.appendChild(e);
     var p = document.createElement('p');
     p.appendChild(document.createTextNode(f.filename + " (" + f.length + " bytes)"));
     e.appendChild(p);
     var img = new Image();
     img.src = f.toDataURL();
     e.appendChild(img);
 });
```

#### Additions 2013
 Modifications for local file support by Mark McArdle
 https://github.com/mmcardle/

#### LICENSE
 Copyright (c) 2010 Ilmari Heikkinen

 Permission is hereby granted, free of charge, to any person obtaining a copy
 of this software and associated documentation files (the "Software"), to deal
 in the Software without restriction, including without limitation the rights
 to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
 copies of the Software, and to permit persons to whom the Software is
 furnished to do so, subject to the following conditions:

 The above copyright notice and this permission notice shall be included in
 all copies or substantial portions of the Software.

 THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
 IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
 FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
 AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
 LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
 OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
 THE SOFTWARE.
