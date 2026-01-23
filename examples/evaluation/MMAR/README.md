

| Models                                  | Size  | Open Source | Avg    | Sound   | Music   | Speech  | Sound-Music | Sound-Speech | Music-Speech | Sound-Music-Speech |
|---|---|---|---|---|---|---|---|---|---|---|
| Random Guess                            | -     | -           | 29.3   | 29.4    | 25.9    | 31.5    | 25.0        | 29.3         | 31.1         | 28.1               |
|---|---|---|---|---|---|---|---|---|---|---|
| **Large Audio Language Models (LALMs)** |       |             |        |         |         |         |             |              |              |                    |
| GPT-4o Audio                            | -     | ❌          | 63.5   | 53.9    | 51.0    | 70.4    | 63.6        | 72.5         | 62.2         | 75.0               |
| Omni-R1                                  | 8.4B  | ✅          | 63.4   | 67.3    | 51.5    | 64.3    | 45.5        | 70.2         | 64.6         | 70.8               |
| DeSTA2.5-Audio  ❤️❤️❤️    | 8B    | ✅          | **50.8**   | **38.18**   | **40.78**    | **59.18**    | **54.55**        | **57.34**         | **58.54**        | **33.33**               |
| GPT-4o mini Audio                       | -     | ❌          | 50.6   | 38.8    | 35.9    | 58.8    | 45.5        | 60.1         | 57.3         | 50.0               |
| R1-AQA                                  | 8.4B  | ✅          | 47.6   | 55.8    | 37.4    | 49.0    | 9.1         | 50.0         | 50.0         | 50.0               |
| SALMONN                                 | 7B    | ✅          | 32.8   | 30.9    | 29.6    | 34.4    | 9.1         | 37.6         | 28.1         | 37.5               |
| Qwen2-Audio                             | 8.4B  | ✅          | 30.4   | 33.9    | 23.3    | 33.0    | 9.1         | 33.0         | 26.8         | 33.3               |
| Qwen2-Audio-Instruct                    | 8.4B  | ✅          | 30.0   | 33.3    | 24.3    | 32.3    | 9.1         | 31.2         | 30.5         | 25.0               |
| Audio Flamingo                          | 2.2B  | ✅          | 26.6   | 32.7    | 21.8    | 24.8    | 18.2        | 30.3         | 24.4         | 25.0               |
| GAMA                                    | 7B    | ✅          | 26.5   | 29.1    | 24.3    | 27.9    | 27.3        | 24.8         | 28.1         | 20.8               |
| Qwen-Audio-Chat                         | 8.4B  | ✅          | 23.5   | 27.9    | 20.4    | 22.1    | 9.1         | 25.2         | 25.6         | 20.8               |
| Audio Flamingo 2                        | 0.5B  | ✅          | 23.0   | 20.6    | 20.4    | 24.2    | 27.3        | 23.9         | 26.8         | 25.0               |
| Audio Flamingo 2                        | 1.5B  | ✅          | 22.9   | 26.7    | 20.9    | 22.8    | 9.1         | 22.9         | 23.2         | 20.8               |
| Audio Flamingo 2                        | 3B    | ✅          | 21.9   | 24.9    | 17.5    | 20.8    | 18.2        | 26.6         | 23.2         | 8.3                |
| LTU                                     | 7B    | ✅          | 19.2   | 19.4    | 19.9    | 14.0    | 18.2        | 24.8         | 22.0         | 16.7               |
| LTU-AS                                  | 7B    | ✅          | 19.0   | 20.0    | 14.1    | 19.1    | 9.1         | 20.6         | 28.1         | 12.5               |
| GAMA-IT                                 | 7B    | ✅          | 17.4   | 22.4    | 16.0    | 12.2    | 36.4        | 22.5         | 14.6         | 12.5               |
| MU-LLaMA                                | 7B    | ✅          | 13.9   | 13.9    | 13.6    | 15.0    | 9.1         | 12.4         | 14.6         | 16.7               |
| MusiLingo                               | 7B    | ✅          | 6.6    | 9.1     | 7.3     | 4.1     | 9.1         | 6.9          | 7.3          | 8.3                |



```bash
python3 inference_desta25_audio_vllm.py -i examples/evaluation/MMAR/mmar-meta.json --data_root my_data/MMAR-audio -o mmar
```


MMAU Evaluation script output:

```
******************************
Modality-wise Accuracy:
sound : 38.18% over 165 samples
music : 40.78% over 206 samples
speech : 59.18% over 294 samples
mix-sound-music : 54.55% over 11 samples
mix-sound-speech : 57.34% over 218 samples
mix-music-speech : 58.54% over 82 samples
mix-sound-music-speech : 33.33% over 24 samples
******************************
Category-wise Accuracy:
Signal Layer : 55.81% over 43 samples
Perception Layer : 41.83% over 404 samples
Semantic Layer : 59.22% over 412 samples
Cultural Layer : 50.35% over 141 samples
******************************
Sub-category-wise Accuracy:
Speaker Analysis : 60.42% over 48 samples
Environmental Perception and Reasoning : 53.69% over 149 samples
Content Analysis : 59.21% over 304 samples
Correlation Analysis : 46.00% over 50 samples
Counting and Statistics : 27.27% over 99 samples
Professional Knowledge and Reasoning : 47.89% over 71 samples
Culture of Speaker : 59.62% over 52 samples
Aesthetic Evaluation : 25.00% over 8 samples
Emotion and Intention : 58.33% over 60 samples
Anomaly Detection : 82.35% over 17 samples
Spatial Analysis : 46.67% over 15 samples
Temporal Analysis : 21.43% over 28 samples
Acoustic Quality Analysis : 44.44% over 18 samples
Music Theory : 41.27% over 63 samples
Audio Difference Analysis : 25.00% over 8 samples
Imagination : 40.00% over 10 samples
******************************
Total Accuracy: 50.80% over 1000 samples
******************************
No prediction count: 0
```