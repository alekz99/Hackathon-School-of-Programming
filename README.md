# Хакатон Школы Программирования

## Анализ записей телефонных разговоров с клиентами МСП

### Команда THOTB 2024

Major sports websites provide text-based broadcasts of matches that can be used to create news. In this paper, a system for summarizing broadcasts in Russian is proposed for generating generalizing news and news that are dedicated to some event in the match. The proposed system consists of three components: a news filter, a selector, and a rewriter. The implemented system showed the best results in comparison with the proposed baselines.

## Классификация клиентов

| Тип клиента | Количество |
|-------|--------|
|Нейтральный| 1299 |
|Негативный| 167 | 
|Заинтересованный| 46 |
|Общение не состоялось| 7 |

## Структура репозитория:

1. **convert_audio_to_text**:
   - inference_open_whisper.ipynb - конвертация аудио в текст, с помощью whisper
   - transcription_diarization.ipynb - конвертация аудио в текст, с помощью whisper и pyannote

2. **speechbox_utils** - скрипт для speechbox (слияние трансрибации и диаризации)

3. **task_1**
   - task_1_v1.ipynb - С помощью регулярных выражений определяем менеджера. Оставили реплики клиента. Разметили небольшой набор данных и дообучили берт для классификации клиентов. 
   - **task_1_v2.ipynb - эту версию отправили на проверку.** С помощью регулярных выражений определяем менеджера. Оставили реплики клиента. Оцениваем каждое предложение в каждом звонке с помощью модели анализа тональности. Затем усредняем, а затем усредняем по звонкам. И получаем классификацию клиентов.
