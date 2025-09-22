# Unreal Insights

Unreal Insights Session Browser를 킨 상태로 게임 접속

* Trace Send localhost default(필요 시 채널 설정으로 대체)
* Trace.Stop

독립 게임 실행으로 테스트 시
* EditorPreferences - Play - Play in Standalone Game
    * Additional Launch Parameters 항목에 아래 내용 추가
        * -trace=cpu,gpu,frame,loadtime,memory,callstack,module -statnamedevents
        * (-statnamedevents 을 추가해야 이벤트가 함수명기반으로 기록됨.)


참고 영상 사이트(한국)
* https://www.youtube.com/watch?v=U0uIiBUKq0Q
* https://www.youtube.com/watch?v=hGLIqru5wnI
* https://www.youtube.com/watch?v=KJUVH_KzLj8