# 📖 useListenStory — Voice Playback & Word Highlighting Hook for Expo Apps

`useListenStory` is a custom React Hook built for Expo (React Native) apps to enhance reading experiences by:

- Playing story content using ElevenLabs voice synthesis (or any TTS).
- Highlighting the currently spoken word in real-time.
- Optionally auto-scrolling to match spoken progress.

Perfect for reading apps, e-learning tools, and accessibility-focused mobile experiences.

---

## 🚀 Features

- 🔊 Voice playback with ElevenLabs or other TTS providers
- 📝 Real-time word highlighting
- 📜 Scroll syncing with spoken words
- ⚙️ Plug-and-play for Expo (React Native)

---

## 💡 Usage Example

```tsx
import { useListenStory } from "expo-listen-stories";

const {
  isPlaying,
  handleStop,
  isLoading,
  currentSpokenWordIndex,
  words,
  togglePlayback,
  loadAudio,
  handleUserScroll,
} = useListenStory(storyText, voice_id, scrollViewRef, wordsPerLine);
```

---

## 💬 Example Integration in Expo App

```tsx
const TabsData = ({
  isLoading,
  words,
  currentWordIndex,
  params,
  isDeep,
  isListen,
}) => {
  return (
    <View>
      <Text>{params?.title}</Text>
      <Text>
        {words.map((word, index) => (
          <Text
            key={index}
            style={{
              backgroundColor:
                currentWordIndex === index ? "#3382b9" : "transparent",
              color: currentWordIndex === index ? "#fff" : "#000",
            }}
          >
            {word}
          </Text>
        ))}
      </Text>
    </View>
  );
};
```

---

## ⚙️ Expo Config (`app.json` or `app.config.js`)

Add your ElevenLabs API key and optional voice model ID to your Expo config under the `extra` field:

```json
{
  "expo": {
    "extra": {
      "SHAZ_ELEVEN_LABS_API_KEY": "sx_xxxxxxx",
      "SHAZ_ELEVEN_LABS_VOICE_MODEL": "(optinal - default => jsCqWAovK2LkecY7zXl4)"
    }
  }
}
```

---

## 📦 Requirements

- React Native with Expo
- ElevenLabs API (get your API key from https://try.elevenlabs.io/lofnqseznu1e)
- `expo-constants` (to access environment values)

---

## 🙌 Support This Project

If you love this feature and want to support the development of voice-powered reading experiences — you can sign up using our ElevenLabs referral link:

### 👉 [**Join ElevenLabs with our referral**](https://try.elevenlabs.io/lofnqseznu1e)

Every sign-up helps us continue building awesome tools like this. Thank you! 💙

---

## 🧠 Credits

Built with ❤️ by [Shahzad Siddique](https://www.linkedin.com/in/shahzadsiddique1)  
📧 Contact: mshahzadsiddique5@gmail.com
