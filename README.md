# 🦖 Dino-EJump - Android App

공룡이 장애물을 점프하여 피하는 모바일 게임입니다!

## 📱 앱 정보

- **앱 이름**: Dino-EJump
- **패키지 이름**: com.evanjo.dinoejump
- **버전**: 1.0.0 (Version Code: 1)
- **최소 Android 버전**: Android 5.0 (API 21)
- **타겟 Android 버전**: Android 14 (API 34)
- **화면 방향**: 가로 모드 (Landscape)

## 🎮 게임 기능

- ✅ 공룡 캐릭터로 선인장 장애물 회피
- ✅ 점프 점수 시스템 및 최고 기록 저장
- ✅ 코인 시스템 및 아이템 상점
- ✅ 파워업 아이템 (별, 배리어, 부활약, 천하무적 사탕)
- ✅ 배경음악 (일반/슈퍼점프/천하무적 모드별)
- ✅ 사실적인 그래픽 (하늘, 공룡, 우주)

## 🛠️ 빌드 방법

### 준비물
1. **Android Studio** (최신 버전 권장)
   - 다운로드: https://developer.android.com/studio

2. **JDK 11 이상**

### 빌드 단계

#### 1. Android Studio에서 프로젝트 열기
```bash
File > Open > DinoEJump-Android 폴더 선택
```

#### 2. Gradle 동기화
- Android Studio가 자동으로 Gradle을 동기화합니다
- 오류 발생 시: `File > Sync Project with Gradle Files`

#### 3. APK 빌드

**방법 A: Debug APK (테스트용)**
```bash
Build > Build Bundle(s) / APK(s) > Build APK(s)
```
- 빌드 완료 후 `app/build/outputs/apk/debug/app-debug.apk` 생성
- 이 APK는 테스트용이며 Play Store에 업로드 불가

**방법 B: Release APK (배포용)**
```bash
Build > Generate Signed Bundle / APK
```

1. **키 생성 (처음만)**
   - `Create new...` 클릭
   - Key store path: 원하는 위치에 저장 (예: `dino-keystore.jks`)
   - Password: 안전한 비밀번호 설정
   - Alias: `dinoejump`
   - 정보 입력 후 OK

2. **APK 옵션 선택**
   - APK 선택
   - Next 클릭

3. **키 정보 입력**
   - 앞서 생성한 키 파일과 비밀번호 입력
   - Build Variants: `release` 선택
   - Finish

4. **APK 위치**
   - `app/build/outputs/apk/release/app-release.apk`

#### 4. 실제 기기에서 테스트

```bash
1. 안드로이드 기기의 USB 디버깅 활성화
   - 설정 > 개발자 옵션 > USB 디버깅 켜기

2. USB로 기기 연결

3. Android Studio에서 Run 버튼 클릭 (▶)
```

## 📦 APK 직접 설치

```bash
# ADB가 설치되어 있다면
adb install app/build/outputs/apk/release/app-release.apk
```

또는 APK 파일을 기기로 전송하고 파일 매니저에서 설치

## 🚀 Play Store 업로드 가이드

### 1. Google Play Console 계정 생성
- https://play.google.com/console
- 개발자 등록 비용: $25 (1회 결제)

### 2. AAB (Android App Bundle) 생성 (권장)

```bash
Build > Generate Signed Bundle / APK > Android App Bundle
```

- APK 대신 AAB를 선택
- 키 정보 입력
- `app/build/outputs/bundle/release/app-release.aab` 생성

### 3. Play Console에서 앱 등록

1. **앱 만들기**
   - 앱 이름: Dino-EJump
   - 기본 언어: 한국어
   - 앱 또는 게임: 게임
   - 무료 또는 유료: 무료

2. **스토어 등록정보**
   - 간단한 설명 (80자)
   - 자세한 설명 (4000자)
   - 스크린샷 (최소 2개)
     - 휴대전화: 1080x1920
     - 태블릿: 1200x1920 (선택사항)
   - 그래픽 이미지 (1024x500)
   - 아이콘 (512x512)

3. **콘텐츠 등급**
   - 설문지 작성
   - 폭력/성적 콘텐츠 없음 체크

4. **대상 고객 및 콘텐츠**
   - 타겟 연령: 모든 연령
   - 광고 포함 여부 선택

5. **앱 콘텐츠**
   - 개인정보처리방침 URL (필요시)
   - 앱 액세스 권한 설명

6. **프로덕션 트랙에 업로드**
   - AAB 파일 업로드
   - 출시 노트 작성

7. **검토 및 게시**
   - 모든 항목 완료 확인
   - "프로덕션으로 출시" 클릭
   - 검토 대기 (1-7일 소요)

## 📝 중요 파일 설명

```
DinoEJump-Android/
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── assets/           # 게임 파일 및 음악
│   │       │   ├── index.html    # 게임 HTML
│   │       │   ├── 일반모드.ogg
│   │       │   ├── 슈퍼점프.mp3
│   │       │   └── 천하무적.mp3
│   │       ├── java/
│   │       │   └── com/evanjo/dinoejump/
│   │       │       └── MainActivity.java  # 메인 액티비티
│   │       ├── res/
│   │       │   ├── mipmap-*/     # 앱 아이콘
│   │       │   ├── values/       # 리소스 값
│   │       │   └── layout/       # 레이아웃 (없음)
│   │       └── AndroidManifest.xml  # 앱 설정
│   ├── build.gradle              # 앱 빌드 설정
│   └── proguard-rules.pro        # 난독화 규칙
├── build.gradle                  # 프로젝트 빌드 설정
├── settings.gradle               # 프로젝트 설정
└── README.md                     # 이 파일

```

## ⚙️ 앱 설정 수정

### 앱 이름 변경
`app/src/main/res/values/strings.xml`
```xml
<string name="app_name">새로운 이름</string>
```

### 패키지 이름 변경
1. `AndroidManifest.xml`의 `package` 속성
2. `build.gradle`의 `applicationId`
3. Java 파일의 패키지 경로

### 화면 방향 변경
`AndroidManifest.xml`에서:
```xml
android:screenOrientation="landscape"  <!-- 가로 -->
android:screenOrientation="portrait"   <!-- 세로 -->
```

## 🐛 문제 해결

### Gradle 동기화 실패
```bash
File > Invalidate Caches / Restart
```

### APK 설치 실패
- "알 수 없는 소스" 설치 허용 확인
- 충분한 저장 공간 확인

### 음악이 재생되지 않음
- 기기 볼륨 확인
- 게임 내 음악 버튼(🔊) 확인

### 앱 크래시
- Logcat 확인: `View > Tool Windows > Logcat`

## 📞 지원

문제가 있으면:
1. Logcat 로그 확인
2. 빌드 오류 메시지 확인
3. Android Studio 최신 버전 사용

## 📄 라이선스

이 프로젝트는 개인 프로젝트입니다.

## 🎉 완성!

앱을 성공적으로 빌드하고 Play Store에 업로드하세요!

---

**Made with ❤️ by EvanJo**
