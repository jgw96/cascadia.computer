---
title: Bringing AI to the Browser - On-Device AI with the Web AI Toolkit
description: Learn how to implement On-Device AI in web apps using Web AI Toolkit for privacy, low latency, and offline capabilities."
date: 2024-12-16
---

Welcome! Today we will be covering On-Device AI for Web Apps. Yes, you can run AI models on the users device, accelerated by a GPU or even NPU all from your web app, no hybrid framework or plugins needed. We will start with what On-Device AI is along with some benefits, and then we will showcase how to get started with AI on the Web with the Web AI Toolkit!

## What is On-Device AI?

On-device AI refers to running AI models directly on the user's device, such as a GPU, NPU, or even a CPU. The key aspect is that the AI model runs locally on the user's machine, not in the cloud.

This approach offers several benefits:

- Privacy: Data processing happens entirely on the device, ensuring user data doesn't leave their machine.
- Latency and Performance: Running models locally can reduce latency and improve performance, depending on the model size.
- Offline Capability: It works even without an internet connection, making it ideal for users with poor network connectivity or who are offline.

### CPU, GPU, NPU???
When running on-device AI, the choice of hardware to run your model on—CPU, GPU, or NPU—can significantly impact performance and application design. 

CPUs are versatile and, obviously, widely available but are not optimized for the immense parallel processing required for running AI models, making them slower for running larger AI models, and potentially heavily impacting battery usage. 

GPUs (Graphics Processing Units), on the other hand, excel at parallel processing, enabling faster execution of AI models, but can still be power-hungry and generate significant heat, especially on laptops or mobile devices.

NPUs (Neural Processing Unit) are specialized hardware designed specifically for AI workloads, offering great performance for a wide variety of models while, maybe more importantly, offering great battery life. They are however, much less common at the moment. 

Choosing the right hardware to run your AI workloads depends on balancing availability, power efficiency, and performance for your target use case, luckily the Web AI Toolkit handles this for you.


Now that we’ve covered the benefits of On-Device AI and hardware considerations, let’s dive into implementing a common AI enabled feature, speech-to-text, using the Web AI Toolkit.

## Web AI Toolkit

### Get Started: Let's implement speech-to-text

Now that we've discussed the benefits of on-device AI, let's talk about how to get started implementing it in your web applications. To make this easier, we'll use a library I wrote called the [Web AI Toolkit](https://github.com/jgw96/web-ai-toolkit). The toolkit's main goal is to simplify building AI features in your web apps. It makes implementing common AI features like speech-to-text and text summarization on-device incredibly easy, all with just two lines of JavaScript.

To get started with the Web AI Toolkit, the first step is to install it from npm by running:
```bash
npm install web-ai-toolkit
```

With the library installed, we are ready to start using the toolkit. The [GitHub README](https://github.com/jgw96/web-ai-toolkit?tab=readme-ov-file#web-ai-toolkit) for the Web AI Toolkit lists all of the available features; with examples of how to use them.

For our example, we'll look at implementing speech-to-text. For speech-to-text, we will import the `transcribeAudioFile` function and pass an audio file (as a Blob) to the function. The function will then return the transcribed text from the audio. 

```javascript
import { transcribeAudioFile } from 'web-ai-toolkit';

const audioFile = ...; // Your audio file Blob
const transcription = await transcribeAudioFile(audioFile);
console.log(transcription);
```
### How it works

The Web AI Toolkit integrates with HuggingFace's powerful [Transformers.js library](https://github.com/huggingface/transformers.js) to run AI models on-device.

For example, for `transcribeAudioFile`, the Web AI Toolkit uses an `AutomaticSpeechRecognitionPipeline` pipeline from the Transformers.js library to actually run the model, which by default is Whisper Tiny. First, some hardware checks will happen, such as using the WebGPU API to get some information about the capabilities of your GPU, if one is available. These checks will help us choose which hardware to run our AI workload on. The toolkit then handles loading the pipeline on demand (and ensuring its only initialized once, a common performance pitfall). If a pipeline is ready to go, or has been newly initialized, it then will prepare the audio from the blob for Whisper, including combining stereo channels into one. Once this is done, the speech-to-text pipeline is ran, returning the text when available. All JavaScript running on the CPU (remember, the actual model itself is being run on the GPU on most devices) is also run in a web worker, ensuring your UI stays smooth and jank free.

## Thanks!

On-device AI in the browser is a game-changer for apps, offering privacy, low latency, and offline capabilities—and potentially reducing your cloud costs. 

Whether you're building next-generation web applications or exploring the potential of AI on the web, the Web AI Toolkit provides the tools you need to get started quickly and efficiently. Ready to try On-Device AI? Install the [Web AI Toolkit](https://github.com/jgw96/web-ai-toolkit) today and build your first AI-powered web app in minutes!

