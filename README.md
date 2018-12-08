---toml
home = true
heroImage = '/hero.png'
actionText = '시작하기 →'
actionLink = '/guide/시작하기/'
footer = 'MIT License | Copyright © 2018-Present Yujin'

[[features]]
title = '성능'
details = 'Rust는 아주 빠르고 메모리 효율적으로 작동합니다. 런타임도, 가비지 컬렉터도 없습니다. 성능이 중요한 서비스, 임베디드, 다른 언어와의 혼용도 준비돼 있습니다.'

[[features]]
title = '신뢰도'
details = 'Rust의 강력한 타입 시스템과 소유권 모델은 메모리 안전성과 스레드 안전성을 보장합니다. 그래서 여러분이 컴파일 할 시점에 많은 종류의 버그를 잡아주죠.'

[[features]]
title = '생산성'
details = '잘 작성된 문서와 도움이 되는 에러 메시지, 내장 패키지 매니저와 빌드 툴, 똑똑한 에디터 지원과 타입 검사, 그 외의 수많은 도구로 생산성이 높아집니다.'
---

# Rust로 뭘 만들 수 있나요?
<div class="capabilities">
<div class="capability">

## 커맨드 라인 도구
Rust 커뮤니티는 활기찬 생태계를 바탕으로 수 많은 커맨드 라인 도구를 만들고 있습니다.
`ls`를 대체하겠다는 [exa](https://github.com/ogham/exa)를 들어보셨나요?
잘 모르는 커맨드 라인을 쓰는 법을 알려주는 [tealdeer](https://github.com/dbrgn/tealdeer)도 있습니다!
Rust의 생산성으로 자신있게 앱을 진화시키고 손쉽게 배포하세요.

![tealdeer](/tealdeer.png)

</div>

<div class="capability">

## 웹 어셈블리
웹앱에 성능이 필요하다면 Rust의 힘을 빌리세요.
[wasm-pack](https://github.com/rustwasm/wasm-pack)을 이용하면 Rust 함수를 JavaScript에서 호출할 수 있고,
npm으로 배포하기도 쉽습니다.
![WebAssembly](/web-assembly-logo.png)

</div>

<div class="capability">

## 네트워크
예상 가능한 퍼포먼스, 효율적인 메모리 사용, 견고한 신뢰성. 네트워크 서비스를 만들기 좋습니다. Rust 라이브러리인 [Reqwest](https://www.github.com/ded/reqwest)와 [Rocket](https://rocket.rs/)의 예시를 살펴보세요.

### Reqwest로 HTTP 요청 보내기
```rust
// 이 코드는 아래 json을 보냅니다
// {"lang":"rust","body":"json"}
let mut map = HashMap::new();
map.insert("lang", "rust");
map.insert("body", "json");

let client = reqwest::Client::new();
let res = client.post("http://httpbin.org/post")
    .json(&map)
    .send()?;
```

### Rocket으로 HTTP 요청 처리하기
```rust
#[derive(FromForm)]
struct Task { name: String, completed: bool }

#[post("/", data = "")]
fn new(task: Form) -> Flash {
    if task.name.is_empty() {
        Flash::error(Redirect::to("/"),
            "Cannot be empty.")
    } else {
        Flash::success(Redirect::to("/"),
            "Task added.")
    }
}
```

</div>

<div class="capability">

## 임베디드
고수준 언어의 편의성을 포기하지 않으면서 저수준의 컨트롤이 필요하다면 Rust가 도움이 될 수 있습니다.

</div>
</div>

<style lang="stylus">
.hero h1
  font-family: 'Alfa Slab One', serif

img[alt=WebAssembly]
  margin 2rem auto

@media screen and (min-width: 720px)
  img[alt=tealdeer]
    display block
    margin 0 auto
    width 70%

  img[alt=WebAssembly]
    display block
    width 40%
    margin 2rem auto

  .capabilities
    display flex
    flex-wrap wrap
    padding 0
    margin -.75rem

  .capability
    flex none
    width 47% // anchor 때문인듯..
    padding .75rem
    margin 0

@media screen and (max-width: 719px)
  .home .features .feature
    padding 0
</style>
