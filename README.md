# banknote-to-coin
A coding challenge to reduce the length of the function

### Task

Write a function that find a minimum amount of coins to exchange a sum of money and then by using any techniques reduce the number of character the function consists of.

### Solution

```
function getCoins(value) {
  const coins = [2, 1, 0.5, 0.2, 0.1, 0.05, 0.01];

  let result = [];
  coins.forEach(coin => {
    while(coin < value) {
      result.push(coin);
      value = value - coin + 0.00001;
    }
  });

  return result;
}
```

### Evolution

```
// function getCoins(value){const coins=[2,1,0.5,0.2,0.1,0.05,0.01];let result=[];coins.forEach(coin=>{while(coin<value){result.push(coin);value=value-coin+0.00001;}});return result;}
// function f(v){const c=[2,1,0.5,0.2,0.1,0.05,0.01];let r=[];c.forEach(c=>{while(c<v){r.push(c);v=v-c+0.00001;}});return r;}
// function f(v){let r=[];[2,1,0.5,0.2,0.1,0.05,0.01].forEach(c=>{while(c<v){r.push(c);v=v-c+0.00001;}});return r;}
// const f=v=>{let r=[];[2,1,0.5,0.2,0.1,0.05,0.01].forEach(c=>{while(c<v){r.push(c);v=v-c+0.00001;}});return r;}
// f=v=>{r=[];[2,1,0.5,0.2,0.1,0.05,0.01].forEach(c=>{while(c<v){r.push(c);v=v-c+0.00001;}});return r;}
// f=v=>{r=[];[2,1,.5,.2,.1,.05,.01].forEach(c=>{while(c<v){r.push(c);v=v-c+0.00001;}});return r;}
// f=v=>{r=[];[2,1,.5,.2,.1,.05,.01].map(c=>{while(c<v){r.push(c);v=v-c+0.00001;}});return r;}
// f=v=>{r=[];[2,1,.5,.2,.1,.05,.01].map(c=>{for(;c<v;v=v-c+0.00001)r.push(c)});return r;}
// f=v=>{r=[];[2,1,.5,.2,.1,.05,.01].map(c=>{for(;c<v;v-=c-1e-9)r.push(c)});return r;}
f=v=>(r=[],[2,1,.5,.2,.1,.05,.01].map(c=>{for(;c<v;v-=c-1e-9)r.push(c)}),r)
```

### Final result

**74 characters**

```
f=v=>(r=[],[2,1,.5,.2,.1,.05,.01].map(c=>{for(;c<v;v-=c-1e-9)r.push(c)}),r)
```
