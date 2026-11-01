# Audio Bridge

Mac과 Galaxy 사이에서 **마지막으로 음악·영상을 재생한 기기로 Bluetooth 이어폰을 전환**하는 앱입니다.
Galaxy에 전화가 오면 통화를 우선하고, Galaxy로 넘길 때 Mac 미디어를 일시정지합니다.
Mac 메뉴바 앱과 Galaxy 보조 앱을 한 쌍으로 사용합니다.

**현재 공개 베타입니다. 최초 실행 시 양쪽 자동 전환은 OFF입니다.**
실제 연결·청취를 확인한 조합은 macOS 26.6.2 + Android 17 / One UI 9.0 + Galaxy Buds4 Pro입니다.
다른 이어폰·OS에서 동일한 동작을 보장하지 않습니다.

## 다운로드

| 파일 | 대상 |
| --- | --- |
| [Mac 설치 파일 · DMG](https://github.com/jangMMSoo/audio-bridge/releases/download/v0.1.0-beta.1/AudioBridge-0.1.0-beta.1-macOS-universal.dmg) | Apple Silicon·Intel, macOS 14.2 이상 |
| [Galaxy 앱 · APK](https://github.com/jangMMSoo/audio-bridge/releases/download/v0.1.0-beta.1/AudioBridge-0.1.0-beta.1-android.apk) | Android 17 이상 |
| [전체 릴리스 및 SHA-256](https://github.com/jangMMSoo/audio-bridge/releases/tag/v0.1.0-beta.1) | ZIP 대체 파일·무결성 확인·변경 내역 |

Intel Mac은 교차 빌드·파일 구조 검사만 통과했으며 실제 Intel 장비 실행은 확인하지 않았습니다.
Android 16 이하에는 자동 연결에 필요한 공개 Bluetooth API가 없어 이 APK를 설치할 수 없습니다.
Mac 앱은 **Developer ID 서명·Apple 공증 전**이며, APK는 Google Play 배포본이 아닙니다.

## 처음 연결하기

1. 같은 이어폰을 **Mac과 Galaxy 각각에 한 번 페어링**합니다. 두 기기를 같은 Wi-Fi에 연결합니다.
2. DMG를 열고 `Buds Bridge.app`을 `Applications`로 끌어 넣은 뒤 실행합니다.
   인터넷에서 받은 앱의 실행이 차단되면 [Mac 설치 안내](USER_GUIDE.ko.md#mac-설치)를 확인하세요.
3. Galaxy에 APK를 설치하고 Audio Bridge를 엽니다. **이어폰 선택 · 등록**에서 같은 이어폰을
   선택하고 사용자 승인 등록을 완료합니다.
4. Mac 메뉴바 `BB OFF`에서 **갤럭시 연결 코드 복사**를 선택합니다. 이 코드를 본인의
   Galaxy로 전달하고 Audio Bridge **설정 → 연결 코드 붙여넣기**에 입력합니다.
   연결 코드는 두 기기의 인증 정보입니다. 공개 게시물·이슈에 올리지 마세요.
5. Mac의 Bluetooth·시스템 오디오·로컬 네트워크 접근과 Galaxy의 근처 기기·전화 상태·알림·
   네트워크 권한을 허용합니다. Galaxy **설정 → 재생 감지 설정 열기**에서
   **Buds Bridge 재생 감지**의 알림 접근도 허용합니다.
6. 양쪽에서 연결 상태를 확인하고 **같은 이어폰**을 선택합니다. 수동 전환으로 양쪽 소리를
   먼저 확인한 뒤, 원할 때 **양쪽 자동 전환을 ON**으로 켭니다.

개발자 모드·USB·무선 디버깅·ADB는 필요하지 않습니다.
자세한 순서와 문제 해결은 **[사용 가이드](USER_GUIDE.ko.md)**를 참고하세요.

## 사용 중

- Mac에서 새로 재생하면 Mac으로, Galaxy에서 새로 재생하면 Galaxy로 전환합니다.
- Mac의 소리가 계속 이어지면 다른 영상의 재생 버튼을 누른 것만으로 새 시작을 구분하지 못합니다.
  재생을 약 3초 멈췄다가 다시 시작해 주세요. 연결 준비 전에 시작한 재생은 자동으로 가져오지 않습니다.
- 전화는 Galaxy 우선입니다. 통화 상태를 확인할 수 없으면 Mac 자동 연결을 보류합니다.
- Mac 메뉴에서 감지 시간·무음 재대기 시간·전환 간격을 조절할 수 있습니다.
- 자동 전환 OFF와 수동 전환을 언제든 사용할 수 있습니다.
- 로그인/재부팅 후 시작은 각 앱 설정에서 켤 수 있습니다. 강제 종료한 앱은 다시 열어야 할 수 있습니다.

## 검증 범위와 한계

Mac↔Galaxy 양방향 실제 소리, 전화 수신 시 전환·이어폰 통화, Mac 일시정지, 자동 OFF와 수동 전환을
확인했습니다. 안정화 테스트와 짧은 재생 측정은 통과했지만 **장시간 재생·실제 절전/재부팅 복귀,
다른 이어폰·Intel 실행은 별도 검증이 필요**합니다. 새 공개 베타의 연결 코드·패키지 검사는
릴리스 노트에 구분합니다. 시스템/드라이버가 절대로 멈추지 않는다는 보장은 하지 않습니다.

Windows판은 이 릴리스에 포함하지 않습니다. 기본 멀티포인트나 제조사 자동 전환으로 충분한
환경에서는 별도 앱이 필요하지 않을 수 있습니다.

## 개인정보와 문의

오디오 세기·재생 상태로 전환을 판단하며 오디오 녹음 파일을 저장하거나 서버로 보내지 않습니다.
두 기기는 같은 네트워크에서 인증된 TLS로 직접 통신합니다. 자세한 항목은 [개인정보 안내](PRIVACY.md)를
확인하세요.

문제는 [Issues](https://github.com/jangMMSoo/audio-bridge/issues)에 OS·앱 버전, 이어폰 모델,
발생 시각, 재현 순서를 알려주세요. 연결 코드·IP·인증키·전화번호 등 개인 정보는 제외해 주세요.

이 저장소는 설치 파일·사용 가이드를 배포합니다. 앱과 소스의 별도 재배포/수정 이용 권한을
부여하는 오픈소스 라이선스는 아직 지정하지 않았습니다. 사용한 외부 라이브러리는 릴리스의
`THIRD_PARTY_NOTICES.zip`에 각 라이선스를 제공합니다.
