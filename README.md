# GemmaLearningLab

**GemmaLearningLab** is a proof-of-concept Android app that leverages Google’s Gemma-3n model to provide offline tutoring for Hungarian kids. It processes screenshots and voice inputs, generates flashcards and quizzes, and delivers interactive learning—all without requiring internet access or subscriptions. Designed as a smart, accessible, and playful learning companion, it aims to support local education effectively.

Hungary’s education system faces significant challenges, including insufficient funding for teachers and resources. Many students rely on private tutors because the formal system often cannot fully address their learning needs. This project tackles these issues by harnessing Gemma-3n’s multimodal capabilities to replicate key functions of a private tutor, running entirely on-device after an initial model download—eliminating the need for continuous internet connectivity or subscription fees.

Part of the [Google Gemma-3n Hackathon](https://www.kaggle.com/competitions/google-gemma-3n-hackathon), this project showcases innovative applications of Gemma-3n to empower learners and help bridge educational gaps in Hungary through accessible, offline AI technology.

---

## Main Features

- Take screenshots of pages from current notes or book chapters → Gemma-3n processes these images.
- (Optional future) Upload a PDF → automatically split into chapters.
- Chat interface for discussion, powered by a retrieval-augmented generation (RAG) agent built from uploaded pages.
- Voice interaction about the content using Gemma-3n’s audio input capabilities (potentially finetuned for Hungarian). Output text can be converted to speech via TTS (great for kids with reading difficulties).
- Flashcard creation from uploaded pages to practice definitions.
- Quiz bank and quiz creation to test kids' knowledge.

---

## Tasks

- Build main features on Kaggle.
- Learn Kotlin basics.
- Develop the Android app in Kotlin using Google’s example project: [Google AI Edge Gallery](https://github.com/google-ai-edge/gallery).
- Deploy the latest Gemma-3n E2B model that supports audio input.
- Finetune Gemma-3n for Hungarian text and audio using [Unsloth](https://docs.unsloth.ai/basics/gemma-3n-how-to-run-and-fine-tune). Await the release of official Gemma-3n notebooks for easier tuning.
- Investigate deploying models with LoRA adapters for efficient finetuning.
- Find and integrate a suitable TTS model.
- Optional: Dynamically adjust the model size based on available VRAM on users’ phones using Gemma-3n’s Matformer architecture.

---

## Notes

- The gemma-3n-E2B-it-int4 model fits into the GPU VRAM of a Samsung S22+.
- Hungarian text generation quality is currently subpar.

---

## Notes for Finetuning

- [Unsloth released a notebook for parameter-efficient training of Gemma-3n on multimodal data](https://colab.research.google.com/github/unslothai/notebooks/blob/main/nb/Gemma3N_%284B%29-Conversational.ipynb)
- [Unsloth: Gemma 3n: How to Run & Fine-tune](https://docs.unsloth.ai/basics/gemma-3n-how-to-run-and-fine-tune)

---

## Datasets to Consider

### Hungarian Text

- [matekadlicsko/hungarian-news-translations](https://huggingface.co/datasets/matekadlicsko/hungarian-news-translations)  
  Translated Hungarian news articles — clear but not popular.  
- [batubayk/HU-News](https://huggingface.co/datasets/batubayk/HU-News)  
  Hungarian news articles without translation.  
- [Bazsalanszky/reddit_hu](https://huggingface.co/datasets/Bazsalanszky/reddit_hu)  
  Database of 140,000 Reddit posts from r/hungary and r/askhungary. Likely biased.  
- **[Helsinki-NLP/opus_books](https://huggingface.co/datasets/Helsinki-NLP/opus_books)**  
  Collection of copyright-free books aligned by András Farkas in multiple languages.  
- [Liling Tan - Old Newspapers](https://www.kaggle.com/datasets/alvations/old-newspapers)  
  Cleaned a subset of HC Corpora newspapers in multiple languages.  
- [emLam (2017)](https://hlt.bme.hu/en/resources/emLam)  
  Language Modeling Benchmark Corpus for Hungarian, similar to the One Billion Word corpus for English.  
- **[ELTE Poetry Corpus](https://github.com/ELTE-DH/poetry-corpus)**  
  Complete poems of 52 Hungarian canonical poets with sound devices and grammatical features in XML format.  
- **[ELTE Novel Corpus](https://github.com/ELTE-DH/regenykorpusz)**  
  Contains 400 Hungarian novels.  
- **[ELTE Drama Corpus](https://github.com/ELTE-DH/drama-corpus)**  
  Contains 74 Hungarian dramas.  
- [SZTAKI-HLT/HunSum-2-abstractive](https://huggingface.co/datasets/SZTAKI-HLT/HunSum-2-abstractive)  
  Over 1.8M unique Hungarian news articles from 27 major Hungarian news websites.  
- [Hungarian Webcorpus 2.0](https://hlt.bme.hu/en/resources/webcorpus2)  
  The largest Hungarian language corpus scraped from the .hu domain.  
- [Hunglish Corpus](http://mokk.bme.hu/resources/hunglishcorpus/)  
  Hungarian-English parallel corpus automatically aligned at the sentence level.  
- [SzegedParallel Corpus](https://rgai.inf.u-szeged.hu/node/163)  
  English-Hungarian parallel corpus was selected based on grammatical and translational criteria.  
- **[Wikibooks Dataset by Dhruvil Dave](https://www.kaggle.com/datasets/dhruvildave/wikibooks-dataset)**  
  Complete text of over 270,000 chapters of Wikibooks in 12 languages.  
- **[Folktales Dataset by Andrzej Panczenko](https://www.kaggle.com/datasets/andrzejpanczenko/folk-tales-dataset)**  
  2,838 folktales from different nations.

### Audio Input

- [KTH / hungarian-single-speaker-tts](https://huggingface.co/datasets/KTH/hungarian-single-speaker-tts)  
- [Mozilla Foundation / Common Voice 17.0](https://huggingface.co/datasets/mozilla-foundation/common_voice_17_0)  
- [ESPnet / Yoda's Granary](https://huggingface.co/datasets/espnet/yodas-granary)  

---

## Useful Info Related to Gemma-3n

- [Gemma 3n model overview](https://ai.google.dev/gemma/docs/gemma-3n)  
- [Introducing Gemma 3n: The developer guide](https://developers.googleblog.com/en/introducing-gemma-3n-developer-guide/)  
- [Gemma-3n Matformer Lab – Useful code for specifying custom model size according to available memory](https://colab.research.google.com/github/google-gemini/gemma-cookbook/blob/main/Gemma/%5BGemma_3n%5DMatFormer_Lab.ipynb)  

---

## Useful Info for LLM Use on Android

- [Google dev – LLM Inference guide for Android](https://ai.google.dev/edge/mediapipe/solutions/genai/llm_inference/android)  
- [Example project – Google AI Edge Gallery](https://github.com/google-ai-edge/gallery)  

---

*Feel free to contribute and help make this private tutor app a reality for Hungarian kids!*
