---
title: "innerHTML vs innerText vs textContent"
date: 2023-02-13 17:03:00 +0530
categories: [notes]
tags: [html,javascript,dom]
toc: true
---
# Difference between innerHTML ,innerText and textContent

```html
<body>
    <div class='outer-div'>
      <div class='inner-div'>
        <p>this is a p tag</p>
        <span>this is a span</span><br>
        <span>this is another span</span>
        <span style="display:none"> this is hidden<span>
      </div>
    </div>

    <div class="empty-div"></div>
</body>
```
```javascript
const innerDiv = document.querySelector('.inner-div');
```
# innerHTML
The innerHTML gets or sets the HTML contained within the element.
* Get the HTML content of an element.

```javascript
innerDiv.innerHTML
```
Output:  
   `'\n        <p>this is a p tag</p>\n        <span>this is a span</span><br>\n        <span style="text-transform:uppercase">this is another span</span>\n        <span style="display:none"> this is hidden<span>\n    </span></span>'`

* Change the HTML content of an element 

```javascript
emptyDiv.innerHTML='<span style="color:red">this is a colored span</span>'
```
Output: It will display  "this is a colored span" with red color style on it in the browser .

Also  read about performance and security issues with using innerHMTL.

# innerText
The  innerText property gets the visible text content of web page. The hidden content cannot be retrieved.  
innerText will turn `<br>` element into newline character.  
If you change the text-transform of an element by CSS, it will affect the result of 'innerText'.

```javascript
innerDiv.innerText
```
Output:  
 `'this is a p tag\n\nthis is a span\nTHIS IS ANOTHER SPAN'`  
Note the uppercase and display hidden style has been applied and `<br>` has been converted to newline character .


# textContent
In textContent, all the text including the hidden contents can be accessed.It ignores styling and is only looking for the non-rendered text content of the nodes.  
```javascript
innerDiv.textContent
```

Output:  
 `'\n        this is a p tag\n        this is a span\n        this is another span\n         this is hidden\n    '`  
Note the uppercase and display style are not applied  and  `<br>` has been ignored . 