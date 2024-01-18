<!-- markdownlint-disable MD030 -->

# Flowise Embed

Javascript library to display flowise chatbot on your website

![Flowise](https://github.com/YiruoAI/FlowiseChatEmbed/blob/main/images/ChatEmbed.gif?raw=true)

Install:

```bash
yarn install
```

Dev:

```bash
yarn dev
```

Build:

```bash
yarn build
```

## Embed in your React App

### PopUp

```jsx
import { BubbleChat } from '@yiruoai/flowise-embed';

const App = () => {
  // groupId和thirdUserId必传参数，用于标识聊天以及用户身份
  return <BubbleChat apptoken="${chatflowToken}" apiHost="${API_HOST}" groupId="" thirdUserId="" />;
};
```

### FullPage

```jsx
import { FullPageChat } from '@yiruoai/flowise-embed';

const App = () => {
  // groupId和thirdUserId必传参数，用于标识聊天以及用户身份
  return <FullPageChat apptoken="${chatflowToken}" apiHost="${API_HOST}" groupId="" thirdUserId="" />;
};
```

## Embed in your HTML

### PopUp

```html
<script type="module">
  import Chatbot from 'https://cdn.jsdelivr.net/npm/@yiruoai/flowise-embed/dist/web.js';
  // groupId和thirdUserId必传参数，用于标识聊天以及用户身份
  Chatbot.initChatInfo({
    apptoken: '${chatflowToken}',
    apiHost: '${API_HOST}',
    groupId: '',
    thirdUserId: '',
  });
</script>
```

### FullPage

```html
<script type="module">
  import Chatbot from './web.js';
  Chatbot.initFull();
  // groupId和thirdUserId必传参数，用于标识聊天以及用户身份
  Chatbot.initChatInfo({
    apptoken: '${chatflowToken}',
    apiHost: '${API_HOST}',
    groupId: '',
    thirdUserId: '',
  });
</script>
<flowise-fullchatbot></flowise-fullchatbot>
```

To enable full screen, add `margin: 0` to <code>body</code> style, and confirm you don't set height and width

```html
<body style="margin: 0">
  <script type="module">
    import Chatbot from './web.js';
    Chatbot.initFull({
      theme: {
        chatWindow: {
          // height: 700, don't set height
          // width: 400, don't set width
        },
      },
    });
    // groupId和thirdUserId必传参数，用于标识聊天以及用户身份
    Chatbot.initChatInfo({
      apptoken: '${chatflowToken}',
      apiHost: '${API_HOST}',
      groupId: '',
      thirdUserId: '',
    });
  </script>
</body>
```

## Configuration

You can also customize chatbot with different configuration

```html
<script type="module">
  import Chatbot from 'https://cdn.jsdelivr.net/npm/@yiruoai/flowise-embed/dist/web.js';
  // groupId和thirdUserId必传参数，用于标识聊天以及用户身份
  Chatbot.initChatInfo({
    apptoken: '${chatflowToken}',
    apiHost: '${API_HOST}',
    groupId: '',
    thirdUserId: '',
  });
  Chatbot.init({
    chatflowConfig: {
      // topK: 2
    },
    theme: {
      button: {
        backgroundColor: '#3B81F6',
        right: 20,
        bottom: 20,
        size: 'medium',
        iconColor: 'white',
        customIconSrc: 'https://raw.githubusercontent.com/walkxcode/dashboard-icons/main/svg/google-messages.svg',
      },
      chatWindow: {
        showTitle: true, // show/hide the title bar
        title: 'Flowise Bot',
        titleAvatarSrc: 'https://raw.githubusercontent.com/walkxcode/dashboard-icons/main/svg/google-messages.svg',
        welcomeMessage: 'Hello! This is custom welcome message',
        backgroundColor: '#ffffff',
        height: 700,
        width: 400,
        fontSize: 16,
        poweredByTextColor: '#303235',
        botMessage: {
          backgroundColor: '#f7f8ff',
          textColor: '#303235',
          showAvatar: true,
          avatarSrc: 'https://raw.githubusercontent.com/zahidkhawaja/langchain-chat-nextjs/main/public/parroticon.png',
        },
        userMessage: {
          backgroundColor: '#3B81F6',
          textColor: '#ffffff',
          showAvatar: true,
          avatarSrc: 'https://raw.githubusercontent.com/zahidkhawaja/langchain-chat-nextjs/main/public/usericon.png',
        },
        textInput: {
          placeholder: 'Type your question',
          backgroundColor: '#ffffff',
          textColor: '#303235',
          sendButtonColor: '#3B81F6',
        },
      },
    },
  });
</script>
```

## License

Source code in this repository is made available under the [MIT License](https://github.com/YiruoAI/FlowiseChatEmbed/blob/main/LICENSE.md).
