# Serge - LLaMa made easy 🦙

![License](https://img.shields.io/github/license/nsarrazin/serge)

A chat interface based on `llama.cpp` for running Alpaca models. Entirely self-hosted, no API keys needed. Fits on 4GB of RAM and runs on the CPU.

- **SvelteKit** frontend
- **MongoDB** for storing chat history & parameters
- **FastAPI + beanie** for the API, wrapping calls to `llama.cpp`

[demo.webm](https://user-images.githubusercontent.com/25119303/226897188-914a6662-8c26-472c-96bd-f51fc020abf6.webm)

## Getting started

Setting up Serge is very easy. TLDR for running it with Alpaca 7B:

```
git clone git@github.com:nsarrazin/serge.git && cd serge

cp .env.sample .env

docker compose up -d
docker compose exec api python3 /usr/src/app/utils/download.py tokenizer 7B
```

(You can pass `7B 13B 30B` as an argument to download multiple models.)

Then just go to http://localhost:8008/ and you're good to go!

## Models

Currently only the 7B, 13B and 30B alpaca models are supported. There's a download script for downloading them inside of the container, described above.

If you have existing weights from another project you can add them to the `api/weights` folder and they will be automatically copied on build.

## What's next

- [x] Front-end to interface with the API
- [x] Pass model parameters when creating a chat
- [ ] User profiles & authentication
- [ ] Different prompt options
- [ ] LangChain integration with a custom LLM
- [ ] Support for other llama models, quantization, etc.

And a lot more!
