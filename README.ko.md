# Yab

또 하나의 브라우저(Yet another browser). Mac을 위한 작고 조용한 브라우저이며, iPhone 앱도 제공합니다.

![왼쪽에 탭이 배치되고, 상품 페이지와 가격을 지켜보는 에이전트가 표시된 Yab](docs/images/readme/window.jpg)

Yab은 군더더기 없는 브라우저입니다. 위쪽이나 왼쪽에 탭 한 줄, 그리고 웹페이지. 그게 전부입니다. 주소 입력과 검색은 하나의 입력창에서 처리합니다.

웹페이지는 모든 Mac에 내장된 **WebKit** 엔진으로 실행됩니다. Apple 실리콘 Mac에서는 탭이나 사이트별로 **Chromium** 엔진을 선택할 수도 있습니다. 이미 구독 중인 AI 서비스의 에이전트를 전용 탭에서 실행할 수 있으며, 에이전트는 비공개 탭에 접근할 수 없습니다.

**[Yab 다운로드](https://yetanotherbrowser.com)** · macOS 15.4 이상 · [새로운 기능](https://yetanotherbrowser.com/changelog) · [사용 설명서](https://yetanotherbrowser.com/manual)

## 주요 기능

- **하나의 입력창.** 주소를 입력하면 해당 페이지로 이동하고, 검색어를 입력하면 검색합니다. 방문 기록을 바탕으로 주소를 자동 완성하며, Return 키를 누르기 전까지는 아무것도 전송하지 않습니다.
- **방해되지 않는 탭.** 고정 탭, 폴더, 스페이스를 지원합니다. 이전 세션의 탭은 즉시 복원되며, 클릭하기 전까지는 리소스를 사용하지 않습니다. `⌘K`로 열려 있는 모든 탭을 찾을 수 있습니다.
- **두 가지 엔진.** 기본 엔진은 WebKit입니다. Apple 실리콘 Mac에서는 필요한 사이트에 Chromium을 사용할 수 있으며, Chrome 확장 프로그램, Chrome DevTools, Chrome 웹 스토어도 지원합니다.
- **차단 및 숨기기 기능 내장.** 광고 차단기가 브라우저 엔진 내부에서 동작해 네트워크 요청이 발생하기 전에 광고를 차단합니다. `⇧⌘H`를 누르면 사이트에서 원하는 요소를 영구적으로 숨길 수 있습니다.
- **읽기 모드, 플로팅 비디오, 분할 보기, Peek.** 각 기능을 단축키 하나로 실행할 수 있습니다.
- **비밀번호는 키체인에.** 기존에 사용하던 비밀번호 관리자를 사용할 수도 있습니다.
- **전용 탭에서 작업하는 AI 에이전트.** 사용자의 로그인 세션을 활용하며, 전송, 결제, 삭제 등의 작업을 수행하기 전에 확인을 요청합니다.
- **종단 간 암호화된 동기화.** Mac과 iPhone 사이의 동기화를 선택적으로 활성화할 수 있으며, 데이터는 종단 간 암호화됩니다.

![네 가지 테마의 읽기 모드](docs/images/readme/reading.jpg)

Yab이 저장하고 전송하는 항목은 [docs/privacy.md](docs/privacy.md)에 한 줄씩 정리되어 있습니다. 전체 단축키 목록은 [docs/keyboard.md](docs/keyboard.md)에서 확인할 수 있습니다.

## 빌드 방법

Xcode 26 이상이 설치된 Mac에서 다음 명령어를 실행합니다.

```bash
git clone https://github.com/yetanotherbrowser/yab.git
```

```bash
cd yab && ./build.sh
```

```bash
open "build/yab Dev.app"
```

위 과정을 거치면 **Yab Dev**가 생성됩니다. Yab Dev는 번들 ID, 설정, 데이터, 키체인 항목이 모두 분리된 개발용 사본이므로 정식 Yab과 함께 실행해도 서로 영향을 주지 않습니다. 임시 코드 서명(ad hoc signing)을 사용하므로 Apple 개발자 계정이 필요하지 않습니다. 테스트는 `swift test`로 실행합니다.

전체 개발 환경 설정, Chromium 탭, iPhone 앱, 각 검증 단계에서 확인하는 내용은 [CONTRIBUTING.md](CONTRIBUTING.md)를 참고하세요. 코드 구조는 [docs/architecture.md](docs/architecture.md)에 정리되어 있습니다.

## 기여하기

Yab에는 제보된 버그가 많아 모두 처리하기에는 일손이 부족합니다. 모든 기여를 환영하며, 특히 버그 수정에 도움이 필요합니다.

- **버그 제보.** [버그 제보 양식](https://github.com/yetanotherbrowser/yab/issues/new/choose)을 이용해 주세요. Yab 버전, macOS 버전, 해당 탭의 엔진(WebKit 또는 Chromium)이 가장 중요한 정보입니다.
- **버그 수정.** [`good first issue`](https://github.com/yetanotherbrowser/yab/labels/good%20first%20issue)와 [`help wanted`](https://github.com/yetanotherbrowser/yab/labels/help%20wanted) 레이블이 붙은 이슈부터 시작할 수 있습니다. 작업 전에 [CONTRIBUTING.md](CONTRIBUTING.md)를 읽어 주세요. 풀 리퀘스트에 필요한 검증 자료가 안내되어 있습니다.
- **보안 문제.** 공개 이슈로 등록하지 말고 [SECURITY.md](SECURITY.md)에 안내된 절차에 따라 비공개로 제보해 주세요.

버그 제보부터 릴리스까지의 과정은 [docs/open-source/process.md](docs/open-source/process.md), 프로젝트의 의사결정 구조는 [GOVERNANCE.md](GOVERNANCE.md)에서 확인할 수 있습니다. 모든 참여자는 [행동 강령](CODE_OF_CONDUCT.md)을 준수합니다.

## 라이선스

라이선스에 대한 자세한 내용은 [LICENSE](LICENSE)를 참고하세요. 앱에 포함된 서드파티 코드와 각 라이선스에서 요구하는 고지 사항은 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)에 정리되어 있습니다.
