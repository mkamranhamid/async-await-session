# Async Await

- ### Lets code

### API call

```javascript
function asyncApi() {
  return new Promise((resolve, reject)=>{
    setTimeout(()=>{
      resolve(1);
    },1500)
  })
}

await asyncApi(); 
```
