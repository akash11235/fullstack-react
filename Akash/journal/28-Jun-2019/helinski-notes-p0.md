call back functions : functions which the browser calls back 
which are defined as event functions within each global objects at window level.  
In the below code section, `xhttp` is a window level object.
We go ahead and define for it standard html event : `onreadystatechange`
so this event is called by the browser once browser is ready to do 
this layer of task(task of calling event functions of associated objects with window object.

[link](https://fullstackopen.com/en/part0/fundamentals_of_web_apps)
>When the state of the object changes, the browser calls the event handler function.
>The function code checks that the readyState equals 4 
>(which depicts the situation The operation is complete) and that 
>the HTTP status code of the response is 200.

>The mechanism of invoking event handlers is very common in JavaScript. Event handler functions are called callback functions. The application code does not invoke the functions itself, but the runtime environment - the browser, invokes the function at an appropriate time, when the event has occurred.

(Clarify `data.forEach..`)


```javascript

var xhttp = new XMLHttpRequest()
xhttp.onreadystatechange = function() {
  if (this.readyState == 4 && this.status == 200) {
    const data = JSON.parse(this.responseText)
      console.log(data)

      var ul = document.createElement('ul')
      ul.setAttribute('class', 'notes')

      data.forEach(function(note) {
          var li = document.createElement('li')

          ul.appendChild(li)
          li.appendChild(document.createTextNode(note.content))
          })

    document.getElementById('notes').appendChild(ul)
  }
  )
```

### The POST Mechanism
if Preserve log checkbox in chrome debugger tool is not checked then the post Request comes quickly in the
network monitor tab and then goes away. 


Notes on single page app(SPA)
> The Notes page of our application bears some resemblance to SPA-style  
...
> The event handler immediately calls the method e.preventDefault() to prevent the default handling of form submit. The default method would send the data to server and cause a redirect, which we don't want to happen.
..

In the SPA example,
>  The form has no action or method attributes to define how and where to send the input data.

> The POST request to the address new\_note\_spa contains the new note as JSON-data containing both the content of the note (content) and the timestamp (date):

> The server responds with statuscode 201 created. This time the server does not ask for a redirect, the browser stays on the same page, and it sends no further HTTP-requests.

