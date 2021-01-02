# Zinteract

COVID-19 has made video conferencing platforms like Zoom ubiquitous, as these platforms remain one of the few means for isolated individuals to enjoy genuine interactions with other people. This, however, raises concerns about accessibility. Why should individuals who struggle with using a keyboard and mouse due to disability and other circumstances be deprived of speaking face-to-face with other people?

Zinteract aims to solve the aforementioned problem of video conferencing monopolizing valuable human interaction combined with limited accessibility of these platforms. Our solution offers gesture-based control of Zoom functions—such as reactions, raise hand, toggle audio input toggle video input—and automatic dictation of Zoom chat messages. This means that the user can simply make a V-symbol (or any of the several available gestures) to send a Thumbs Up reaction or mute their audio. They can also make a gesture to begin dictation of their speech, which is automatically typed and sent into the Zoom chat box.

To enable the gesture-based control of Zoom functions, we computed landmarks of the user's hand using a TensorFlow model published by Google MediaPipe, and then used heuristics based on those landmarks to estimate gestures. We then associated particular gestures with Zoom actions, hooking into Zoom via a GUI automation testing framework, and running an appropriate bridge function when a particular gesture is detected. To automate dictation of chat messages, the user first performs an associate gesture to begin dictation. We then stream audio to Google Cloud Platform's Speech-to-Text API, receive the transcription, and type the transcription into Zoom chat via a bridge function.

Built for [HopHacks Fall 2020](https://devpost.com/software/ten-thirty-tech-team) at the Johns Hopkins University
- Winner of Best Healthcare Hack presented by Siemens Healthineers
