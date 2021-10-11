### CAESAR CIPHER

```javascript
function rot13(str) {
  const splitString = str.split("");
  let newString = [];

  const UPPERS = [
    "A",
    "B",
    "C",
    "D",
    "E",
    "F",
    "G",
    "H",
    "I",
    "J",
    "K",
    "L",
    "M",
    " ",
    "!",
    "?",
    ".",
  ];
  const LOWERS = [
    "N",
    "O",
    "P",
    "Q",
    "R",
    "S",
    "T",
    "U",
    "V",
    "W",
    "X",
    "Y",
    "Z",
    " ",
    "!",
    "?",
    ".",
  ];

  for (let i = 0; i < str.length; i++) {
    if (UPPERS.includes(splitString[i])) {
      newString.push(LOWERS[UPPERS.indexOf(splitString[i])]);
    } else {
      newString.push(UPPERS[LOWERS.indexOf(splitString[i])]);
    }
  }

  return newString.join("");
}

console.log(rot13("SERR PBQR PNZC"));
```
