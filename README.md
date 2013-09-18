# Upload Preview jQuery Plugin

## What is that?

This jQuery plugin provides an easy way to preview your uploads before they're actually uploaded to the server. So if you selected an image or audio file from your hard drive, it will generate a live preview of the selected image or audio player for the audio file.

***

## How it works?

To get access to the not uploaded data, we can use the HTML5 file reader api. This api provides reading local files. This step is pretty important, because we need to this data in order to show it in the browser window. To get more information about the file reader, you can read the (offical documentation) [http://www.w3.org/TR/FileAPI/].

***

## Download

jquery.uploadPreview.js (2.5 kb)
jquery.uploadPreview.min.js (1.3 kb)

***

## Installation

**1. Copy jQuery & plugin:**

    <script type="text/javascript" src="http://code.jquery.com/jquery-2.0.3.min.js"></script>
    <script type="text/javascript" src="assets/js/jquery.uploadPreview.min.js"></script>

**2. Set up your upload form e.g.:**

    <div id="image-preview">
      <label for="image-upload" id="image-label">Choose File</label>
      <input type="file" name="image" id="image-upload" />
    </div>

**3. Load the plugin function as often as you need and fill it with the parameters:**

    <script type="text/javascript">
    $(document).ready(function() {
      $.uploadPreview({
        input_field: "#image-upload",   // Default: .image-upload
        preview_box: "#image-preview",  // Default: .image-preview
        label_field: "#image-label",    // Default: .image-label
        label_default: "Choose File",   // Default: Choose File
        label_selected: "Change File",  // Default: Change File
        no_label: false                 // Default: false
      });
    });
    </script>

***

## Customization

You're free to customize the CSS and HTML for the input, preview & label fields. Feel free to change it as you wish. There's no need that you put it all together as you can see in step 2. The preview box might be located somewhere else on your page as the input field is.

***

## Image File Example

    <style type="text/css">
    #image-preview {
      width: 400px;
      height: 400px;
      position: relative;
      overflow: hidden;
      background-color: #ffffff;
      color: #ecf0f1;
      input {
        line-height: 200px;
        font-size: 200px;
        position: absolute;
        opacity: 0;
        z-index: 10;
      }
      label {
        position: absolute;
        z-index: 5;
        opacity: 0.8;
        cursor: pointer;
        background-color: #bdc3c7;
        width: 200px;
        height: 50px;
        font-size: 20px;
        line-height: 50px;
        text-transform: uppercase;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        margin: auto;
        text-align: center;
      }
    }
    </style>

    <script type="text/javascript">
    $(document).ready(function() {
      $.uploadPreview({
        input_field: "#image-upload",
        preview_box: "#image-preview",
        label_field: "#image-label"
      });
    });
    </script>

    <div id="image-preview">
      <label for="image-upload" id="image-label">Choose File</label>
      <input type="file" name="image" id="image-upload" />
    </div>

***

## Audio File Example

    <style type="text/css">
    #audio-preview {
      background: #ffffff;
      width: auto;
      padding: 20px;
      display: inline-block;
    }

    #audio-upload {
      cursor: pointer;
      background-color: #bdc3c7;
      color: #ecf0f1;
      padding: 20px;
      font-size: 20px;
      text-transform: uppercase;
    }
    </style>

    <script type="text/javascript">
    $(document).ready(function() {
      $.uploadPreview({
        input_field: "#audio-upload",
        preview_box: "#audio-preview",
        no_label: true
      });
    });
    </script>

    <div id="audio-preview">No file selected</div><br />
    <input type="file" name="audio" id="audio-upload" />

***

## License

**The MIT License (MIT)**

Copyright (c) 2013 Opoloo GbR

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