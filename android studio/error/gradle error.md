ⅠⅡⅢ1️⃣0️⃣2️⃣✅
### Ⅰ. Gradle Error
#### 1️⃣ Gradle Version Error
✅ 에러
```java
Gradle DSL method not found: 'dependencyResolutionManagement()'
Possible causes:
Your project may be using a version of the Android Gradle plug-in that does not contain the method (e.g. 'testCompile' was added in 1.1.0).
```

✅ 원인
- 현재 사용하고 있는 Android Gradle Version 인 Gradle DSL 이 'dependencyResolutionManagement()'를 메서드를 포함하지 않아서 발생한 문제
- 'dependencyResolutionManagement()' 메서드는 Gradle 7.0 부터 도입
- 따라서, Android Gradle 플러그인의 이전 버전에서 지원하지 않음

✅ 해결 방법
- 현재 Gradle Plugin 확인 하기
- build.gradle(Project) 파일
``` java
plugins {
    id 'com.android.application' version '8.2.2' apply false
    id 'com.android.library' version '8.2.2' apply false // 추가
    id 'org.jetbrains.kotlin.android' version '1.9.20' apply false // 추가
}
```
- id 'com.android.library' version '8.2.2' apply false 설정 안됨 ( 추가 완료 )
- id 'org.jetbrains.kotlin.android' version '1.9.20' apply false 설정 안됨 ( 추가 완료 )

### Ⅱ. Build 에러
#### 1️⃣ Build Configuration Language ( 빌드 구성 )
✅ Build Configuration Language
- 프로젝트 빌드 구성을 정의하는 언어

✅ 안드로이드 빌드 구성
- 앱 : [ 소스 코드 ] → ( 컴파일 ) → ( 패키지 화 )
- 위 작업을 위한 설정 / 규칙을 지정 ( 빌드 구성 언어로 규칙 지정 )

✅ Kotlin DSL
- Kotlin 으로 작성된 Domain-Specific Language
- 안드로이드 개발에서는 Kotlin DSL 을 사용하여, Gradle 빌드 스크립트를 작성하는 것을 권장
