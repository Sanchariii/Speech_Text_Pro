# Speech Text Pro

A React.js application that converts spoken words from a microphone into text and allows users to copy the transcribed text to their clipboard.

[Visit the Demo](https://example.com)


## How it works
`useSpeechRecognition` is a React hook that gives a component access to a transcript of speech picked up from the user's microphone.

`SpeechRecognition` manages the global state of the Web Speech API, exposing functions to turn the microphone on and off.

## Table of Contents

- [Features](#features)
- [Demo](#demo)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Features

- Real-time speech-to-text conversion.
- Easy one-click copy of transcribed text to clipboard.
- User-friendly interface.

## Demo
<img width="916" alt="image" src="https://github.com/Sanchariii/Speech_Text_Pro/assets/88083502/36187c23-9e7a-4e25-a189-a10b5913e335">


You can view a live demo of this project [Visit the Demo](https://example.com).

## Getting Started

### Prerequisites

Before you begin, ensure you have met the following requirements:

- Node.js and npm installed on your local machine.
- A compatible web browser.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/speech-to-text-converter.git

2. To import in your React code:

`import SpeechRecognition, { useSpeechRecognition } from 'react-speech-recognition'`

### Usage

## Detecting when the user denies access to the microphone

Even if the browser supports the Web Speech API, the user still has to give permission for their microphone to be used before transcription can begin. They are asked for permission when `react-speech-recognition` first tries to start listening. At this point, you can detect when the user denies access via the `isMicrophoneAvailable` state. When this becomes `false`, it's advised that you disable voice-driven features and indicate that microphone access is needed for them to work.

```
if (!isMicrophoneAvailable) {
  // Render some fallback content
}
```
## Controlling the microphone

Before consuming the transcript, you should be familiar with `SpeechRecognition`, which gives you control over the microphone. The state of the microphone is global, so any functions you call on this object will affect _all_ components using `useSpeechRecognition`.

### Turning the microphone on

To start listening to speech, call the `startListening` function.

```
SpeechRecognition.startListening()
```

This is an asynchronous function, so it will need to be awaited if you want to do something after the microphone has been turned on.


## Resetting the microphone transcript

To set the transcript to an empty string, you can call the `resetTranscript` function provided by `useSpeechRecognition`. Note that this is local to your component and does not affect any other components using Speech Recognition.

```
const { resetTranscript } = useSpeechRecognition()
```

## Continuous listening

The microphone will stop listening when the user preses the stop listening button. This reflects the approach taken by "Stop Listening" buttons on modern devices.

```
SpeechRecognition.startListening({ continuous: true })
```



 ### Contributing
Contributions are welcome! Feel free to open issues or submit pull requests to help improve this project. Please follow the Contributor Covenant and the Pull Request Guidelines.

### License
This project is licensed under the MIT License
