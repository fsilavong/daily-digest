# Mistral News Digest

## Speaking of Voxtral | Mistral AI
Original URL: https://mistral.ai/news/voxtral-tts

- Mistral presents Voxtral TTS as a 4B-parameter text-to-speech model for high-quality multilingual voice generation with low latency and enterprise-scale usability [1](./citations/1.md).
- The model is described as a transformer-based, autoregressive, flow-matching TTS system built on Ministral 3B, with a 3.4B transformer decoder backbone, a 390M flow-matching acoustic transformer, and a 300M neural audio codec [1](./citations/1.md).
- The input path uses a 5–25 second voice prompt plus text; the system predicts semantic tokens per audio frame and then uses the flow-matching transformer to generate acoustic latents. Mistral says its in-house codec processes audio causally with semantic VQ and acoustic FSQ latents at 12.5 Hz [1](./citations/1.md).
- Reported claims include state-of-the-art multilingual voice generation in 9 languages, realistic emotionally expressive speech, very low time-to-first-audio, easy adaptation to new voices, and zero-shot cross-lingual voice adaptation [1](./citations/1.md).
- In human evaluations, Mistral says Voxtral TTS outperforms ElevenLabs Flash v2.5 on naturalness while keeping similar TTFA, and matches ElevenLabs v3 quality with emotion steering. The page emphasizes that automated metrics such as WER and audio-quality scores are not sufficient for naturalness, so results rely on comparative human evaluations by native speakers [1](./citations/1.md).
- The page says the model is released with open weights under a CC BY-NC 4.0 license. If the claims hold, the model may be useful for low-latency, customizable, multilingual voice agents and speech-to-speech systems [1](./citations/1.md).
