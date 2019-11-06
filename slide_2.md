# Async Await

- ### Lets code

### before

```javascript
function request() {
  return fetch('./api/some.json')
  .then(
	   function(response) {
            if (response.status !== 200) {
              console.log('Looks like there was a problem. Status Code: ' + response.status);
              return;
            }
            // Examine the text in the response 
             response.json().then(function(data) {
	             console.log(data);
             });
	}).catch(
		function(err) {
            console.log('Fetch Error :-S', err);
    });
}

request().then((success)=>{ ... }).catch((err)=>{ ... }); 
```

### now

```javascript
async function request() {
	try {
		const response = await fetch('./api/some.json');
		if (response.status !== 200) {
			console.log('Looks like there was a problem. Status Code: ' + response.status);
	        return;
		}
		const data = await response.json();
		console.log(data);
		return data;
	} catch(err) {
		console.log('Fetch Error :-S', err);
		throw err;
	}
}

await request(); 
```