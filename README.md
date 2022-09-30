## Ecole
#### JQuery-port

**WPF, XAML**로 개발된 카카오톡을 **html, css3**를 이용해 클로닝 했던 프로젝트를 변형시켜 포트폴리오 형태로 만들었다.

#### Code
```HTML5
  <head>
    <link rel="stylesheet" href="styles.css" />
    <script src="jquery.mobile/jquery-1.11.1.min.js"></script>
	  <script src="jquery.mobile/jquery.mobile-1.4.5.min.js"></script>
	
	  <script src="cordova.js"></script>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>KaKao Clone</title>
  </head>
```
디바이스 해상도에 따라 **반응형 웹**을 구현하기 위해 **viewport** 사용

**width=device-width** -> 페이지의 너비를 기기의 스크린 너비 설정, 렌더링 영역을 기기의 크기와 같게 만들어줌

**initial-scale=1.0** -> 페이지 로딩시 원래 크기를 사용하도록 함.

```HTML5
<html lang="en">
```
한국형 웹 콘텐츠 접근성 지침(KWCAG) 2.1에는 웹페이지의 head 요소 안에 페이지의 기본 언어 선언을 규정하고 있다.

lang 속성에 명시된 값을 통해 스크린 리더가 인식을 하기 때문.

본 프로젝트에서는 영어만을 사용하였기 때문에 lang 속성 값을 en 만 할당

```HTML5
<i class="fas fa-wifi"></i>
<i class="fas fa-battery-full fa-lg"></i>
<i class="fas fa-bolt"></i>
<i class="fas fa-search fa-lg"></i>
<i class="fas fa-music fa-lg"></i>
```
[아이콘] (https://fontawesome.com/how-to-use/on-the-web/referencing-icons/basic-use)

##### css3
```css3
#no-mobile {
    position: absolute;
    z-index: 99;
    height: 100vh;
    background-color: var(--yellow);
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 32px;
    top: 0;
  }
  @media screen and (max-width: 645px) {
    #no-mobile {
      display: none;
    }
  }
```
##### HTML5
```HTML5
<div id="no-mobile">
      <span>Your screen is too big 😭</span>
</div>
```
화면 크기가 특정크기 초과시 경고화면으로 전환

##### CSS3
```CSS3
  .nav__btn {
    transform: translateY(50px);
    opacity: 0;
    animation: appearBtnAnimation 0.3s ease-in-out forwards;
  }
  
  .nav__btn:nth-child(2) {
    animation-delay: 0.2s;
  }
  .nav__btn:nth-child(3) {
    animation-delay: 0.5s;
  }
  .nav__btn:last-child {
    animation-delay: 0.8s;
  }
```
화면 전환시 아이콘 애니메이션이 시간차를 두고 나타나는 것을 표현

