# Unreal Insights

## 세션 실행 및 설정

Unreal Insights Session Browser를 킨 상태로 게임에 접속하여 프로파일링을 시작할 수 있습니다.

-   **Trace Send**: `localhost` (기본값). 필요 시 채널 설정으로 대체할 수 있습니다.
-   **Trace Stop**: `Trace.Stop` 명령어로 트레이스를 중지합니다.

### 독립 게임 실행 시 설정

독립 게임(Standalone Game)으로 테스트를 실행할 경우, 다음 설정을 추가해야 합니다.

1.  **Editor Preferences** > **Play** > **Play in Standalone Game**으로 이동합니다.
2.  **Additional Launch Parameters** 항목에 아래 내용을 추가합니다.

    ```
    -trace=cpu,gpu,frame,loadtime,memory,callstack,module -statnamedevents
    ```

    > **Note**: `-statnamedevents` 옵션을 추가해야 이벤트가 함수명 기반으로 기록되어 가독성이 향상됩니다.

## 커스텀 스코프 프로파일링

코드 내 특정 구간의 성능을 측정하고 싶을 때 `TRACE_CPUPROFILER_EVENT_SCOPE` 매크로를 사용할 수 있습니다.

이 매크로를 사용하면 지정된 코드 블록의 실행 시간을 측정하여 Unreal Insights의 타이밍 트랙에 커스텀 이벤트를 생성합니다.

### 사용 예시

```cpp
void AMyActor::MyFunction()
{
    // "MyActor::MyFunction" 이라는 이름으로 Unreal Insights에 타이밍 이벤트가 생성됩니다.
    TRACE_CPUPROFILER_EVENT_SCOPE(TEXT("MyActor::MyFunction"));

    // 성능을 측정하고 싶은 코드
    // ...
}
```

## 참고 영상 사이트 (한국)

-   [https://www.youtube.com/watch?v=U0uIiBUKq0Q](https://www.youtube.com/watch?v=U0uIiBUKq0Q)
-   [https://www.youtube.com/watch?v=hGLIqru5wnI](https://www.youtube.com/watch?v=hGLIqru5wnI)
-   [https://www.youtube.com/watch?v=KJUVH_KzLj8](https://www.youtube.com/watch?v=KJUVH_KzLj8)
