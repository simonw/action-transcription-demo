# Action Transcription

## Team Members

Simon Willison - [@simonw](https://twitter.com/simonw) - [simonwillison.net](https://simonwillison.net/)


## Tool Description

Action Transcription supports archiving and searching the transcripts of videos from multiple different video hosting platforms.

It runs on GitHub to take advantage of the free GitHub Actions code running mechanism - but importantly it does not require, or use any tools aside from the user's browser, even to setup new instances of the tool.

If a video has captions, this tool can be used to retrieve and store those captions.

If a video does not have captions, the tool can extract the audio from the video and run it through [Whisper](https://openai.com/blog/whisper/) - a new, state-of-the-art speech-to-text tool from OpenAI.

## Installation

This GitHub repository acts as a "template repository" - you can create your own copy of the repository [using this form](https://github.com/simonw/action-transcription/generate).

These can be created public or private - public repos get an additional feature and are free to run, while private repos have additional cost.

If you wish to use the "Whisper" integration you will need to create an account on [Replicate](https://replicate.com/), then copy the API token from that account and create a new GitHub Actions secret in your repository called `REPLICATE_API_TOKEN`. Transcribing videos costs money - usually around $0.20 per minute of audio.

## Usage

Usage of the tool is through filing GitHub Issues.

Issues must include the URL to the video you want to transcribe in the issue body.

You can tag the issue with "captions" to extract captions from the video hosting provider (which is free), or "whisper" to transcribe the audio using Whisper (which costs money).

The results of the operation will be posted in a comment on the issue, and will also be written to the GitHub repository for permanent storage.

## Additional Information

The pattern I am most excited about here is the way this shows that GitHub Issues can be used to create a hopefully not-too-intimidating interface for users, which can trigger real code to be run for free by the GitHub Actions platform.

My next step with this project will be to add a custom search engine that can be used to search the transcripts of the videos. I intend to build this using [Datasette Lite](https://lite.datasette.io/).
