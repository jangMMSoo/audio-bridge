# Audio Bridge 0.1.0-beta.1

Mac과 Galaxy를 한 쌍으로 사용하는 첫 공개 베타입니다. 설치 후 자동 전환은 양쪽 모두 OFF입니다.

## 다운로드

- **Mac:** `AudioBridge-0.1.0-beta.1-macOS-universal.dmg` — macOS 14.2 이상,
  Apple Silicon + Intel 통합. DMG를 열고 `Buds Bridge.app`을 Applications로 옮기세요.
- **Galaxy:** `AudioBridge-0.1.0-beta.1-android.apk` — Android 17 / API 37 이상.
- DMG 대신 앱 ZIP도 제공합니다. 설치법은 [사용 가이드](https://github.com/jangMMSoo/audio-bridge/blob/main/USER_GUIDE.ko.md)를 참고하세요.
- `SHA256SUMS.txt`는 파일 무결성 확인용, `THIRD_PARTY_NOTICES.zip`은 외부 라이브러리 라이선스,
  `RELEASE-METADATA.json`은 빌드·검증 범위입니다. 기기 연결 코드와 인증정보는 포함하지 않습니다.

## 처음 사용하기

1. 같은 이어폰을 Mac과 Galaxy에 각각 페어링하고 같은 Wi-Fi에 연결합니다.
2. 두 앱을 설치하고 필요한 권한을 허용합니다. Galaxy에서 이어폰 선택·사용자 승인 등록과 재생 감지 알림 접근을 완료합니다.
3. Mac 메뉴의 **갤럭시 연결 코드 복사**에서 같은 Wi-Fi의 주소를 선택합니다.
4. 코드를 본인 Galaxy의 **설정 → 연결 코드 붙여넣기**에 입력합니다. 개발자 모드/ADB는 필요하지 않습니다.
5. 같은 이어폰을 선택하고 수동 양방향 소리를 확인한 뒤 양쪽 자동 전환을 ON으로 켭니다.

연결 코드는 비밀번호처럼 취급하세요. 이슈·스크린샷·공개 채팅에 올리지 마세요.

## 포함 기능

재생 시작에 따른 전환, 전화 우선, Galaxy 양도 시 Mac Pause, 이어폰 선택, 수동 전환,
자동 OFF, Mac 감지 시간 조절, 반복 연결 차단과 실패 상태를 제공합니다.
감지 콜백·대기열·재시도에 상한을 두고, 저장 실패 시 실제 자동 정책도 OFF로 처리합니다.

## 검증과 제한

- Mac 정책 36개 + 네이티브 33개 테스트, Clippy·포맷·통합 빌드 통과.
- 새 연결 코드 형식과 네이티브 메뉴/단일 요청 동작 검사 통과. 새 코드로 실제 Galaxy를 처음 등록하는 전체 과정은 별도 실기기 확인이 필요합니다.
- DMG 체크섬·실제 마운트·서명·앱 ZIP 일치·두 아키텍처·최소 macOS 버전 검사 통과.
- APK 서명·debuggable=false·백업 비활성화·버전/SDK·개인키 제외 검사 통과.
  초기 개발판과 서명 ID를 유지합니다. 공개 APK 자체의 새 실기기 설치는 아직 확인하지 않았습니다.
- 기존 전환 구현은 macOS 26.6.2 + Android 17 / One UI 9.0 + Buds4 Pro에서 양방향 청취,
  전화 우선과 Mac Pause를 확인했습니다. 공개 패키지 검사와 기존 실기기 결과는 구분합니다.
- **Developer ID 서명·Apple 공증 전**입니다. Mac에서 앱별 실행 승인이 필요할 수 있습니다.
  [Apple 공식 안내](https://support.apple.com/en-us/102445)를 따르세요. 보안 기능 전체를 끌 필요는 없습니다.
- Intel은 교차 빌드만 확인했습니다. 장시간 재생·실제 절전/재부팅·다른 이어폰은 미검증입니다.
- Android 16 이하는 설치 대상이 아닙니다. 이 APK는 Play Store 배포본이 아닙니다.
- IPv4 Wi-Fi/LAN을 사용합니다. VPN/게스트망/방화벽 환경에서는 연결이 제한될 수 있습니다.
- Windows와 유료 결제 기능은 이번 릴리스에 포함하지 않습니다.

사용법과 설치 파일을 공개하며, 앱 소스의 별도 이용/재배포 라이선스는 아직 부여하지 않았습니다.
[개인정보 안내](https://github.com/jangMMSoo/audio-bridge/blob/main/PRIVACY.md)와
[문제 제보](https://github.com/jangMMSoo/audio-bridge/issues)를 확인하세요.
