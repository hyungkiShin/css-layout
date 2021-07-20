### FLEX_BOX 
```
FLEX_BOX 는 children 과 얘기하지 않는다 ! 
이말은 
ex ) .box {
        bla`bla`bla
    }
    .box:nth-child(n) { // 자식 요소를 하나하나 컨트롤 한 일이 없다는 뜻이다.

    }

    그럼 자식요소는 어떻게 건들까.
    먼저 자식들의 "부모" 를 만들어준다. ( 제일 가까이 있는 부모를 만들어주자.)

    부모는 통상 "display: flex;" 인 상태이다.

    그렇게 만들어진 부모는 ( 항상 자식 위에 붙어있는 존재...) 는 자식을 컨트롤 할 수 있다.

    자식들의 위치를 바꾸고자 한다면, flex container (부모) 안에 있어야 한다.

```

### flex-direction
```
flex container 를 또다른 말로 flex-direction 이라고 부를수 있다. default 값은 항상 row 이다.
2가지의 case 가 존재하는데.
하나는 -> row (가로)
둘째는 -> column (세로) 이다.

flex-direction: row 일때 main-axis 는 ( 가로)
                cross-axis 는 (세로) 가 된다.
                column 일때 main-axis 는 (세로)
                cross-axis 는 (가로) 가 된다.

                방향 이 90도 로 회전한다고 보면된다. 
                개 중요하다. ( 여기서 좀 고비다.ㅜ)
```

### flex-direction 을 이용한 조작.
```
    position 의 속성 중 하나인 justify-content 를 이용해 자식들을 조작할 수 있다.
    justify-content 는 수평축 에 있는 flex children 의 위치를 변경한다.

    ex) .wrapper {
            display:flex;
            justify-content: center;
        }
        justify-content 속성을 이용해 자식들의 위치를 center 로 옮기면. browser 가 이들을 
        계산에 위치를 조정해 준다. (Cool...)

    justify-content 는 각 속성 마다재미있는 기능잉 있는데, 
    center : 중앙정렬 
    space-between: box 사이에 공간을 줌
    space-around: box 주변 옆 공간을 같게 만든다.
```

### 자주 마주치는 문제
```
    우물안 개구리를 아는가? 
    우물속에 있는 존재는 자신의 위치가 어딘지 모른다.
    꼭 넓은 세상에 좋은 개발자 잘하는 개발자가 많다는것을 모르는 경험없는 자기 자신처럼. (그게나얍~빠~둠빠 두비~두밤)
    
css
---
    .wrapper {
        display:flex;
        justify-content: center;
        align-items: center;
    }
    .box {
        width: 200px;
        height: 200px;
        background: blue;
        color: white
    }

---
html
<!DOCTYPE html>
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Test</title>
</head>
<html>
    <body>
        <div class="wrapper">
            <div class="box">1</div>
            <div class="box">2</div>
            <div class="box">3</div>
        </div>
    </body>
</html>

자 위와 같은 코드가 있을때 box 들이 맨위에서 가운데로 모여있고 끝인기분을 느끼게 되는데..
위의 코드 베이스에 css 해석을 해보면 
-> justify-content: center 로 해주면 

자식들을 뭉탱이로 가운데로 몰아준다고 생각하면 된다.

-> align-items:center;
자식들 요소 를 부모 "높이" 에서 가운데로 몰아준다.

눈치 쳇는가...!!
"부모의 높이가 없다면, 자식은 그대로 다.
왜? 부모 높이가 없다면 이미 중앙이니까."

만약 이와 같이 발생하는 경우 "어 뭐야 왜 그대로야" 하는 일들이 없었음 좋겠다. 

잘모르겠다 -> wrapper 클래스에 height:900px 정도 줘보자.

* align-items 의 기본값은 start 다.

column ( 가로가 세로로 되는 마술을 겪어보고 싶다면 wrapper 클래스 내부에 다음코드를 ...!)
.wrapper {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    height: 100vh;
}
```
