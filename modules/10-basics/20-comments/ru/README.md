
Кроме кода, в файлах с исходным кодом могут находиться комментарии. Это текст, который не является частью программы и нужен программистам для пометок. С их помощью добавляют пояснения, как работает код, какие здесь ошибки нужно поправить или не забыть что-то добавить позже.

```javascript
// Удалить строку ниже после реализации задачи по регистрации
console.log(10);
```

Комментарии в JavaScript бывают двух видов:

## Однострочные комментарии

*Однострочные комментарии* начинаются с `//`. После этих двух символов может следовать любой текст, вся строчка не будет анализироваться и исполняться.

Комментарий может занимать всю строчку. Если одной строчки мало, то создаются несколько комментариев:

```javascript
// For Winterfell!
// For Lanisters!
```

Комментарий может находиться на строчке после какого-нибудь кода:

```javascript
console.log('I am the King'); // For Lannisters!
```

## Многострочные комментарии

*Многострочные комментарии* начинаются с `/*` и заканчиваются на `*/`.

```javascript
/*
  The night is dark and
  full of terrors.
*/
console.log('I am the King');
```

Такие комментарии, обычно, используют для документирования кода, например, функций.
