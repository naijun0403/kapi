<h1 align="center">ChannelList</h1>

> **Note**: 아직 개발 중인 구조입니다. 구조를 수정하고 싶으시면 고민 없이 PR을 넣어 주세요.

## get: `function(channelId: number): ChannelList`

`channelId`에 해당하는 채널을 반환합니다.

### example

```javascript
const client = BotProject.getClient();

client.channelList.get(channelId);
```