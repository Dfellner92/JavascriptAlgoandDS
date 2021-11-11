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

### Telephone Number Validator

Return `true` if the passed string looks like a valid US phone number.

```javascript
function telephoneCheck(str) {
  if (str.length >= 10 || str.length <= 14) {
    if (
      str[0] === "2" ||
      str[0] === "3" ||
      str[0] === "4" ||
      str[0] === "5" ||
      str[0] === "6" ||
      str[0] === "7" ||
      str[0] === "8" ||
      str[0] === "9"
    ) {
      if (str.length === 10) {
        return true;
      } else if (
        (str[3] === " " && str[7] === " ") ||
        (str[3] === "-" && str[7] === "-")
      ) {
        return true;
      }
    } else if (str[0] === "1") {
      if (str[1] === " ") {
        if (
          (str[5] === " " && str[9] === " ") ||
          (str[5] === "-" && str[9] === "-")
        ) {
          return true;
        } else if (str[2] === "(") {
          if (str[6] === ")" && str[11] === "-") {
            return true;
          }
        }
      } else if (str[1] === "(") {
        if (str[5] === ")" && str[9] === "-") {
          return true;
        }
      }
    } else if (str[0] === "(") {
      if (str[4] === ")" && str[8] === "-") {
        return true;
      }
    }
  }
  return false;
}

console.log(telephoneCheck("555-555-5555"));
console.log(telephoneCheck("8oo-six427676;laskdjf"));
console.log(telephoneCheck("1 555)555-5555"));
```
