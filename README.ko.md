# MSYS2로 C++ 환경 구성 및 VS Code 사용 가이드

이 문서는 Windows에서 MSYS2를 설치하고, g++로 `main.cpp`를 만들고, VS Code에서 여는 과정을 정리합니다.

## 1) 준비물

- MSYS2 다운로드: [https://www.msys2.org/](https://www.msys2.org/)
- VS Code 설치: [https://code.visualstudio.com/](https://code.visualstudio.com/)

## 2) MSYS2 설치 및 업데이트

1. MSYS2 설치 파일을 실행해 기본 경로로 설치합니다.
2. 설치 완료 후 "MSYS2 UCRT64" 터미널을 실행합니다.
3. 패키지를 최신 상태로 업데이트합니다.

```bash
pacman -Syu
```

업데이트로 터미널이 종료되면 다시 "MSYS2 UCRT64"를 열고 한 번 더 실행합니다.

```bash
pacman -Syu
```

## 3) C++ 컴파일러 설치

UCRT64 환경 기준으로 GCC를 설치합니다.

```bash
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-gcc
```

설치 확인:

```bash
g++ --version
```

## 4) 작업 폴더 생성

예시로 `C:\Users\user\Desktop\CHJ\helloGroup\cpp` 폴더를 사용합니다.

```bash
mkdir -p /c/Users/user/Desktop/CHJ/helloGroup/cpp
cd /c/Users/user/Desktop/CHJ/helloGroup/cpp
```

## 5) main.cpp 생성

아래 내용으로 파일을 생성합니다.

```bash
cat > main.cpp << 'EOF'
#include <iostream>

int main() {
    std::cout << "Hello, MSYS2 + VS Code!" << std::endl;
    return 0;
}
EOF
```

## 6) VS Code에서 열기

MSYS2 UCRT64 터미널에서 폴더를 엽니다.

```bash
code .
```

VS Code가 열리면 `main.cpp`를 확인합니다.

## 7) 빌드와 실행 (선택)

```bash
g++ main.cpp -o main.exe
./main.exe
```

## 8) 문제 해결 체크리스트

- `g++` 인식 실패: UCRT64 터미널에서 실행했는지 확인
- `code` 명령 실패: VS Code가 PATH에 추가되어 있는지 확인
- 빌드 오류: 현재 디렉터리와 파일명 확인

---
