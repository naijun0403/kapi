<h1 align="center">MessageEvent</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## 개요
메세지가 올때 발생하는 이벤트입니다.

## `message`
### example
```javascript
client.on('message', (data) => {
   if (data.message === '!ping') {
       data.room.send('pong!');
   } 
});
```

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
    send: async function () { [native code] },
    sendAllRoom: async function () { [native code] }, // 지금까지 수신된 모든방에 채팅을 보냄
    markAsRead: async function () { [native code] },
  },
  packageName: '패키지 명',
  chat: {} // 알림에 담겨오는 데이터 (android.os.Bundle)
}
```