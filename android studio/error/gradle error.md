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
