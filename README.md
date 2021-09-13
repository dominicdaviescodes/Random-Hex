# Random-Hex

Hex has numbers and letters, which we'll need to generate randomly.

We can convert num to str using toString().
If we leave toString() empty js defaults to base 10 (0-9).

```js
let color = Math.random().toString();
// 0.45617865432
```

Hex is 0-9 then A - F which is base 16.

```js
color = Math.random().toString(16);
// 0.25b098aa28cb
```
### .substring()
We only need a length of 6 for hex.

.substring() will extract a chunk of characters from a string starting at and ending at specified places.

```js
// start at pos 2 end at 8
color = Math.random().toString(16).substring(2, 8);
// 0.995d15ab342e gives us 995d15
```

### the generateColor function will do a couple of things.

* generate randomColor
* we will change the background color of the body by setting backgroundColor to "#" + randomColor;
* update the hex value shown in the UI by setting the innerHTML to "#" + randomColor


```js
const hex = document.querySelector(".hex")
const btn = document.querySelector(".generate")

const generateColor = () => {
  const randomColor = Math.random().toString(16).substring(2, 8)
  document.body.style.backgroundColor = "#" + randomColor
  hex.innerHTML = "#" + randomColor
}

btn.addEventListener("click", generateColor)

// on page load
generateColor()
```