# Vibes Only V11 — Native Kotlin Android Port

This project is a native Android/Kotlin conversion of the supplied `main.py` V11 engine. The Kivy UI has been replaced with native Android Views.

## Included V11 functionality

- Local JSON knowledge and memory storage
- Private per-user memory
- Q&A teaching and bulk learning
- Text/study/note ingestion
- Categorized knowledge buckets
- Fuzzy memory recall and duplicate detection
- Safe math evaluator
- Web search using DuckDuckGo HTML and Wikipedia REST fallback
- Direct URL fetching with HTTP/HTTPS and private-target checks
- Web/PDF/YouTube/image/text digestion
- PDF extraction using PDFBox Android
- Image OCR using ML Kit
- Project stages, project siphoning, autofill and project ideas
- Revision, flashcards, tests and grading
- Training job history and analytics
- Notifications
- Safety filtering and audit hash chain
- User/role commands
- Theme switching
- Text-to-speech toggle
- Native Android file picker
- Dynamic PNG toolbar: every PNG in `app/src/main/assets/` except `icon.png` becomes a tappable button

## Build with Android Studio

Open this folder in Android Studio with JDK 17. Sync the Gradle project, then run the `app` configuration or use **Build > Generate App Bundles or APKs > Generate APKs**.

## Build from a terminal or GitHub Actions

The GitHub Actions workflow installs Gradle directly, so a generated Gradle wrapper JAR is not required in this archive.

Use:

```bash
gradle :app:assembleDebug
```

The APK is written to:

```text
app/build/outputs/apk/debug/app-debug.apk
```

## PNG buttons

Put button images in:

```text
app/src/main/assets/
```

Recognized names include:

```text
menu.png
send.png
emoji.png
file.png
clear.png
copy.png
settings.png
about.png
new_chat.png
history.png
refresh.png
```

`icon.png` is reserved for the launcher icon and is not added to the runtime toolbar.

For an unrecognized PNG, the app displays a safe fallback dialog so the button still works without crashing.

## Important source-port note

The uploaded V11 Python source is a local-first learning assistant. It includes web retrieval/digestion but does not contain a live external LLM chat call. This Kotlin port preserves that behavior instead of inventing a new model backend.
