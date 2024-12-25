# Callback

**Callback** функсияест, ки ҳамчун аргумент ба функсияи дигар пешниҳод мешавад ва баъдтар дар дохили он функсия даъват мешавад. Одатан, callback-ҳо дар амалиётҳои асинхронӣ истифода мешаванд.

## Чӣ тавр кор мекунад?

Функсияро метавон ҳамчун аргумент ба функсияи дигар дод, ва ин функсия фақат вақте даъват мешавад, ки вақти мувофиқ фаро расад.

### Мисоли оддӣ

```javascript
function greeting(name) {
    console.log(`Салом, ${name}!`);
}

function processUserInput(callback) {
    const name = "Алишер";
    callback(name); // даъвати callback
}

processUserInput(greeting);
```

---

## Асинхронӣ бо Callback

Callback-ҳо боштар дар амалиётҳои асинхронӣ истифода мешаванд, ба монанди интизорӣ дар вақти ворид кардани маълумот ё посух аз сервер.

**Мисол бо setTimeout:**

```javascript
console.log("Оғоз");

setTimeout(() => {
    console.log("Маълуот бор шуд.");
}, 2000);

console.log("Анҷом");
```

**Натиҷа:**
```
Оғоз  
Анҷом  
Маълуот бор шуд.  
```

---

## Callback Hell

Вақте callback-ҳо ба ҳам вобаста мешаванд, код метавонад душворфаҳм шавад, ки онро "Callback Hell" меноманд:

```javascript
setTimeout(() => {
    console.log("1");
    setTimeout(() => {
        console.log("2");
        setTimeout(() => {
            console.log("3");
        }, 1000);
    }, 1000);
}, 1000);
```

**Ҳалли масъала:**  
Барои осон кардани идоракунии код, аз **Promises** ё **async/await** истифода бурдан мумкин аст.

---

## Мисол бо Callback ва API

```javascript
function getDataFromServer(url, callback) {
    console.log("Маълуот дархост шуд...");
    setTimeout(() => {
        const data = { name: "JavaScript", year: 1995 };
        callback(data); // интиқоли маълумот ба callback
    }, 2000);
}

function handleResponse(response) {
    console.log("Маълуот дастрас шуд:", response);
}

getDataFromServer("https://example.com/api", handleResponse);
```

---

## Хулоса

- **Callback** асоси бисёре аз механизмҳои асинхронӣ дар JavaScript мебошад.
- Барои идора кардани пайдарпайиҳои мураккаб, **Promises** ё **async/await** беҳтар аст.
- Callback бояд ба таври дуруст ташкил шавад, то кодро осонфаҳм нигоҳ дорад.


