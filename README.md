# Lazy Image Loader

### 문제 정의

이 문제는 이미지 lazy loading을 구현하는 문제입니다. intersection observer를 사용하세요. viewport에 보이기 전까지는 이미지가 로딩되지 않다가, viewport를 넘어가면 이미지가 표시되어야 합니다.

### getting started

1. 이 repo를 clone 합니다.
2. cmd + shift + p를 눌러서 disable completions을 칩니다. (코파일럿 자동완성 끄기)
3. 로컬에서 npm i를 진행 한 후 npm run start로 브라우저에 띄우세요.
4. 구현한 코드를 각자 github에 push한 뒤 공유하세요.
5. cmd + shift + p를 눌러서 enable completions를 칩니다. (코파일럿 자동완성 키기)

### 꼭 알아두어야 할 것

- 이미지를 로딩시킨 후에는 이미지 태그에 loaded 클래스를 추가하세요.

### IntersectionObserver 기본 사용법

1. IntersectionObserver 인스턴스를 생성하고, 관찰하는 요소가 뷰포트에 들어오거나 나갈 때 실행될 콜백 함수를 전달합니다.
2. observe 메소드를 사용하여 타겟 요소 관찰을 시작합니다.

Example:

```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry) => {
    // 뷰포트에 들어옴
    if (entry.isIntersecting) {
      // 들어온 엘리먼트는 entry.target으로 접근이 가능
    }
  });
}, {}); // 여기에 IntersectionObserver 옵션값이 들어감

// 이미지가 뷰포트에 보이는지 옵저빙 시작
observer.observe(document.querySelector("img"));

// 이미 뷰포트에 보인 후에는 옵저빙 할 필요 없음
observer.unobserve("target element");
```
