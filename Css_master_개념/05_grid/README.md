### grid
```
grid 도 똑같아. 
flex box 에서 가장 인접한 부모에게서 child 의 형태를 조작 할 수있지 ? 

father class 에게 grid 를 먹이고 시작하자.

in css 

.father {
  display: grid;
  grid-template-columns: 250px 250px 250px;
  grid-template-rows: 100px 50px 300px;
  /* column-gap: 10px;
  row-gap: 10px; */
  gap: 10px;
}

.child {
  flex-basis: 30%;
  background: peru;
  color: white;
  font-size: 5px;
  display: flex;
  justify-content: center;
  align-items: center;
}

in html 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div class="father">
        <div class="child">1</div>
        <div class="child">2</div>
        <div class="child">3</div>
        <div class="child">4</div>
        <div class="child">5</div>
        <div class="child">6</div>
        <div class="child">7</div>
        <div class="child">8</div>
        <div class="child">9</div>
    </div>
</body>
<link rel="stylesheet" href="./styles.css">

</link>
</html>


위 코드를 실행 해보면 ,
grid 의 design 은 
항상 father 에서 시작한다.

display:grid 부터 적고 시작 (부모)

grid-template-columns: 셀 마다 가로 길이가 ( width ) 적용 되었음 하는 px ( 픽셀 ) 을 적어주고, 셀 간 자간을 적용하고자 할땐 
row-gap column-gap 을 
공통은 gap 속성을 사용하면 된다.

가로 (main-axis): grid-template-columns
세로 (cross-axis): grid-template-rows 

가로 길이 정해주거나 세로길이 정해줄때 반복적인 작업이 빡칠수 있다.
그럴때 css 에서 제공하는 함수인 
repeat([몇개?],[몇픽셀?]) 만 정해주면 된다.
ex ) grid-template-columns: repeat(4,700px) 처럼 말이다.

물론 repeat 대신에 auto 를 적어줄수도 있다. 


사람들이 주로 아는 grid layout 은 
grid-template-areas: 로 짠다.
이건 table 영역 짜는것과 느낌이 약간 비슷하다.

grid-template-areas: 
"header header header header"
"content content content nav"
"content content content nav"
"footer footer footer footer";

헤더가 가로4 content 가 가로 3 로우 2
nav 가 가로 1 세로 2 
푸터가 가로 4
먹는다고 생각하면 되는데 중요한점은 
header ,content , nav , footer 각 클래스 네임이 grid-template-areas 에 적혀있는 name 과 같아야 한다.


.header {
    background-color: #2ecc71;
    grid-area: "header" 
}

처럼 말이다.

header 에게 column 과 row 가 어디서 시작하고 어디서 끝날지 얘기할 수 있다.

grid-column-start: 1 
grid-column-end: 2 

이경우 반드시 구문 해석이 헷갈릴꺼다.
첫번째 셀부터 2번째 셀까지 아냐 ? 
아니다.
사각형을 생각해보자 
왼쪽면과 오른쪽면 위 아래 면이 있을껀데, 왼쪽면이 1 오른쪽 면이 2 라고 생각하면 된다.
그럼 grid-column-start:1
grid-column-end:3 이면 ?
사각형 두개에 왼쪽 면까지 가 범위다.

```


```css
.father {
  display: grid;
  grid-template-columns: repeat(4,100px);
  grid-template-rows: repeat(4,100px);
  gap: 10px;
}

.header {
  background-color: #2ecc71;
  grid-column-start:1;
  grid-column-end:5;
}

.content {
  background-color: peru;
}

.nav {
  background-color: aqua;
}

.footer {
  background-color: blanchedalmond;
}
```
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div class="father">
        <div class="header">1</div>
        <div class="content">2</div>
        <div class="nav">3</div>
        <div class="footer">4</div>
       
    </div>
</body>
<link rel="stylesheet" href="./styles.css">

</link>
</html>
```

```txt
위 code 를 실행 시켜보면 알 수 있다. 
```

```
위와 같이 layout 을 일일히 
grid-column-start,end 
grid-row-start, end 
로 layout 을 짜기엔 간지가 안난다.
지름길이 없냐 ? 
있다.

grid-column: 1 / 5; 
grid-row: 2 / 4; 
이런식으로 계산해서 떄려 넣을수 있다.

숫자는 간지가 안난다 ! 
span 은 이영역을 차지하겠다 라는 의미로 볼수 있는데 바로 이 span 을 사용하면 된다. 
```

### fr
```
fr 은 fraction 의 약자로 
픽셀이나 % 같은 측정 단위다

father 의 넓이 를 주면 그안에서 해결
넓이를 주지 않으면 body 전체를

(*) 주의할점 ! 높이를 주지 않으면 안된다 사라져 ! 

```


