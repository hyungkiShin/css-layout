### justify-items

```text
minmax 는 최소사이즈다.
줄어들 수 있는 최소 사이즈를
픽스 해두고 그이상 줄어 들지 않는 화면을 짜보자.
  .grid {
  display: grid;
  gap: 10px;
  height: 5px;
  grid-template-columns: repeat(5, minmax(100px, 1fr));
  grid-template-rows: repeat(4, 100px);
}

.item:nth-child(odd) {
  background-color: #2ecc71;
}

.item:nth-child(even) {
  background-color: #3498db;
}
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="stylesheet" href="./styles.css" />
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <div class="grid">
      <div class="item">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item">4</div>
      <div class="item">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item">4</div>
      <div class="item">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item">4</div>
      <div class="item">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item">4</div>
    </div>
  </body>
</html>
```

```css
.grid {
  color: white;
  display: grid;
  gap: 5px;
  grid-auto-rows: 100px;
  margin-bottom: 30px;
}

.item:nth-child(odd) {
  background-color: #2ecc71;
}

.item:nth-child(even) {
  background-color: #3498db;
}

.grid:first-child {
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
}

.grid:last-child {
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" href="./styles.css">
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    auto-fill
    <div class="grid">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div>
        <div class="item">4</div>
        <div class="item">5</div>
    </div>
    auto-fit
    <div class="grid">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div>
        <div class="item">4</div>
        <div class="item">5</div>
    </div>
</body>

</html>
```

```csstext
max-content 는 box 를 컨텐츠에
필요한 만큼 커지는거고

min-content 는 box 를 컨텐트가
작아질 수 있는만큼 작아지는것이다.
글씨를 깨지게 한다던가,
```
