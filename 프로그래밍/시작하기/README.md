---toml
prev = '/프로그래밍/'
next = '/프로그래밍/기초-문법/'

permalink = '/프로그래밍/시작하기/'
sidebarDepth = 4
---

# 시작하기
## Rustup: Rust 버전 관리 도구
Rust를 설치하는 가장 좋은 방법은 Rustup을 이용하는 것입니다. Rustup은 Rust를 설치해주고 Rust의 버전을 관리해줍니다.

### macOS, Linux에서 설치
Rustup을 설치하려면 터미널을 열고 아래의 명령을 실행시켜 주세요.
```bash
$ curl https://sh.rustup.rs -sSf | sh
```

### Windows에서 설치
[rustup-init.exe](https://win.rustup.rs) 파일로 설치하세요.

## Cargo: Rust 빌드 툴과 패키지 매니저
Rustup을 설치했다면 Rust의 빌드 툴이자 패키지 매니저인 Cargo도 함께 설치되었습니다. Cargo로 첫 Rust 프로젝트를 시작해봅시다.
```bash
cargo new hello-rust
```
위의 명령을 실행하면 새 폴더 `hello-rust/` 안에 아래와 같은 파일들이 생깁니다.

    hello-rust/
    ├── Cargo.toml
    └── src/
        └── main.rs

`Cargo.toml` 파일은 이 프로젝트의 매니페스트 파일입니다. 프로젝트의 설정과 이 프로젝트에서 사용하고 있는 의존성을 저장합니다.

`src/main.rs`이 우리가 코드를 작성할 파일입니다. 파일을 열어보면 Cargo가 "Hello, world!"를 출력하는 프로그램을 미리 작성해둔 것을 확인할 수 있습니다.

```rust
fn main() {
  println!("Hello, world!");
}
```

이제 실행을 해 볼까요?

```bash
$ cargo run
```

아래와 같은 메시지가 나왔다면 성공입니다.

```bash
Compiling hell-rust v0.1.0 (/Users/yujingaya/Developer/hello-rust)               
 Finished dev [unoptimized + debuginfo] target(s) in 2.34s                    
  Running `target/debug/hello-rust`
Hello, world!
```