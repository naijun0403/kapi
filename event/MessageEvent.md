<h1 align="center">MessageEvent</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## struct
```json5
{
  message: '메세지',
  sender: {
    name: '보낸사람',
    profileBase64: '보낸사람 프사 base64로 인코딩한 문자열',
    profileHash: 'profileBase64의 hashcode'
  },
  room: {
    name: '방 이름',
    isGroupChat: function () { [native code] }, // 자스 엔진에서 변수임에도 불구하고 function으로 처리함
    send: function () { [native code] },
    sendAllRoom: function () { [native code] }, // 지금까지 수신된 모든방에 채팅을 보냄
    markAsRead: function () { [native code] },
  },
  packageName: '패키지 명',
  chat: Bundle // 알림에 담겨오는 데이터
}
```