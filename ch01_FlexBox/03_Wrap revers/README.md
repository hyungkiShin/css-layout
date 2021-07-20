### wrap 
```
flex_box 는 width 가 깨지든 말든 ㅈ도 신경쓰지 않는다.
오직 같은 줄에 있도록 만드는 데만 신경쓴다.
width 의 크기를 깨뜨려서라도 말이다.

flex-wrap 의 기본값은 nowrap 이다. 

wrap 은 flex_box 에게 child 의 크기를 보장해 달라고 이야기 하는것이다.


css 
.wrapper { 
    display: flex;
    justify-content: space-around;
    height: 100vh;
    flex-wrap: wrap;
}

.child {
    background: blue;
    width:200px;
    height: 200px;
    display: inline-block;
    color: white;

    display: flex;
    justify-content: center;
    align-items: center;
}

    <div class="wrapper">
        <div class="child">1</div>
        <div class="child">2</div>
        <div class="child">3</div>
        <div class="child">4</div>
        <div class="child">5</div>
        <div class="child">6</div>
    </div>
<link rel="stylesheet" href="./styles.css">

    한변 flex-wrap: nowrap 과 wrap 을 번갈아 가며 실행 시켜 보면. 확연히 다른것 을 알 수 있을 것이다.
    

* flex_box 는 reverse 도 갖고 있다. 

wrapper 클래스에 flex-direction: column-reverse 혹은 row-reverse 를 적용해보면 html 은 전혀 변하지 않았지만 자식 element 들은 변한것을 알 수 있다.

* 자매품 flex-wrap: wrap-reverse 도 있다.

wrap 된 상태라고 가정하면, row 단위 수직 기준 사이사이 간격이 있는것을 알 수 있다.
이공간을 수정할 수도 있는데
align-content 를 이용해 수정할 수 있다. 언뜻 보면 justify-content 랑 비슷해보이는데...? 할수 있지만 오노노 align-content 는 Line 에 대한것이다.

wrapper 클래스에 align-content: space-between 을 적용해보면 사이 간격 조정이 끝과 끝으로 적용 된 것을 확인 할 수 있다. 물론, space-around 등등 도 가능하다


```