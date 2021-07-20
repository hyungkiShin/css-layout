### align-self
```
align-self 는 align-items 와 비슷한 일을 하는데
box 하나만 조진다. (자식입장)

.wrapper { 
    display: flex;
    justify-content: space-around;
    height: 100vh;
}

.child {
    background: blue;
    width:200px;
    height: 200px;
    display: inline-block;
    color: white;
}

.child:nth-child(2) {
    align-self: center;
}

---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div class="wrapper">
        <div class="child">1</div>
        <div class="child">2</div>
        <div class="child">3</div>
    </div>
</body>
<link rel="stylesheet" href="./styles.css">

</link>
</html>

위의 코드를 실행시켜보면 가운데 자식만 가운데 삐죽 나와있다.
겁나 반항하는것 처럼 말이다.

자식 클래스에 nth-child(n) 을 붙여 각각 을 컨트롤 할 수 있다.

주의할 점은 wrapper 클래스에 ( 자식에게 가장 인접한 부모 클래스)
높이 가 없다면 전혀 움직이지 않는다는 점을 명심하자.

```

### order 
```
    자식끼리의 순서를 바꾸는 방법이다. 간혹 html 의 자식 element 의 "순서" 를 바꾸기 귀찮을때 사용하면 좋을듯 해보인다.
    nth-child(n) {
        order: 0 // -> default
    } 각각 order 를 다르게 줘보자. ex ) 3번 자식을 order:2 로 

```