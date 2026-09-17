# LumiLearn 📚✨

A single-screen Android app, built with **MIT App Inventor**, that helps young learners build vocabulary through flashcards — each card pairs a picture, a word, and a simple sentence, with text-to-speech to read them aloud.

## How it works

1. The app opens on card 1 of 10, showing a picture, its word, and a short sentence about it
2. Tap **Next** / **Prev** to move through the flashcard deck
3. Tap the "say word" button to hear the word spoken aloud
4. Tap the "say sentence" button to hear the full sentence spoken aloud
5. A counter at the top shows your progress (e.g. "card 3 of 10")

## Features

- 🖼️ Flashcard deck pairing an image, word, and sentence for each item
- ⏭️⏮️ **Next** / **Prev** navigation with boundary checks (won't go past card 1 or 10)
- 🔊 Text-to-speech playback for both the word and the sentence
- 🔢 Live card counter showing current position in the deck
- 🔄 Auto-loads the first card on app launch

## Tech Stack

- **Platform:** MIT App Inventor (block-based, no native code)
- **Components:** `LabelCounter`, `LabelWord`, `Labelsentence`, `Imagecard`, `Buttonnext`, `Buttonprev`, `Btnsayword`, `Buttonsaysentence`, `TextToSpeech1`
- **Variables:**
  - `global current_index` — tracks which card is currently displayed
  - `global wordlist` — the 10 vocabulary words (Apple, Bus, Cat, Dog, Moon, Sun, Square, Parrot, Note, Carrot)
  - `global imagelist` — matching image filenames for each word
  - `global sentencelist` — a short descriptive sentence for each word
- **Procedure:** `updatecard`

## How the Blocks Work

| Event / Procedure | Action |
|---|---|
| `Screen1.Initialize` | Calls `updatecard` to load the first card |
| `updatecard` | Sets `LabelCounter` to "card X of 10", and updates `LabelWord`, `Imagecard`, and `Labelsentence` using `current_index` to look up the matching item in each list |
| `Buttonnext.Click` | If `current_index` is less than 10, increments it and calls `updatecard` |
| `Buttonprev.Click` | If `current_index` is greater than 1, decrements it and calls `updatecard` |
| `Btnsayword.Click` | Calls `TextToSpeech1.Speak` with the current `LabelWord` text |
| `Buttonsaysentence.Click` | Calls `TextToSpeech1.Speak` with the current `Labelsentence` text |

## Example

| Card | Word  | Sentence                  |
|------|-------|----------------------------|
| 1    | Apple | Apple is a fruit           |
| 4    | Dog   | Dog is an animal           |
| 6    | Sun   | Sun is yellow in colour    |
| 10   | Carrot| Carrot is a vegetable      |

## Screenshot

![App Screenshot](https://github.com/aloshikhs-a11y/LumiLearn/blob/main/WhatsApp%20Image%202026-09-17%20at%2011.57.28%20AM.jpeg)

*The blocks editor showing the flashcard data, navigation, and text-to-speech logic.*

## Limitations (v1.0)

- Fixed deck of 10 words — not user-editable within the app
- No quiz or self-check mode (purely browsing/listening)
- No progress saved between sessions
- Single fixed language for words and sentences

## Future Improvements

- Add a quiz mode to test recall of words and meanings
- Let users add their own words, images, and sentences
- Track learning progress across sessions
- Add support for multiple languages

---
*Built as a mini project — MIT App Inventor, block-based development.*
