Some snippets that I have made/collected.
Put in `%appdata%\Code\User\Snippets`

## Javascript
### Javascript CSS Injector
This function injects css into head of the document. 
Example: 
```jsx
 CSSInjector(`
	body {
		margin: 0;
		padding: 0;
		background-color: #0e0e0e
		color: #fff;
	}
`)
```

### Location Change 
Not going to lie grabbed this from stackexchange. Mainly used for one-page style websites, checks for url changes and executes whatever functions or commands you want.
Put the commands or functions you want to run inside the eventListener.

### Self-Invoking Function
Just shorthand for a self-invoking function

### Debounce
Runs the specified function, starts a timer, then only executes the function again if the timer has run out. Useful for observers or other events that trigger often. 

### createAndAppend
Helper function that creates an element and attaches it to the attachpoint. It allows for definition of classes and ids directly in the creation of the element. You can also optionally change the way it appends to attachpoint, the options are: 
appendChild, 
before, 
after, 
insertBefore, 
and insertLast.
Usage:
```jsx
createAndAppend("div.container.background-blue#mainContainer", document.body)
```
To reference the element you have created assign a variable to the createAndAppend function like this:
```jsx
const cancelButton = createAndAppend("button#cancel.button", document.body)
const submitButton = createAndAppend("button#submit.button", cancelButton, "after")
cancelButton.innerHTML = "Cancel"
submitButton.innerHTML = "Submit"
submitButton.style.setProperty("margin-left", "0.5em")
```

## CSS
### !
Just some default css 

## Batch
### Batch Color
Defines some colors that can be used for echoing information.
Example:
```bat
echo %ESCerror% Could not find file!
echo %ESCsuccess% Completed Successfully!
```
Or if you want to color an entire line:
```bat
echo %ESCerrorclr% This is the error message %ESCres%
```
If using the colors directly be sure to reset the color at the end of the line with `%ESCres%`

### Escape Message
This function escapes strings with special characters. Do not forget to enable delayed expansion (setlocal EnableDelayedExpansion).
Example: 
```bat
set  "scarymessage=(sca>ry| mess(a^^ge!)"
call :escape_special_characters  "%scarymessage%"
echo  !msg_escaped!

Output:
^(sca^>ry^| mess^(a^^^^ge^)
```
