# 🎙️ Голосовой ассистент Alex

Голосовой ассистент на Python с использованием TTS модели Kokoro для Google Colab. Ассистент отвечает на приветствия и простые вопросы голосом.

## ✨ Возможности

- 🔊 Голосовой вывод ответов (TTS)
- 📝 Распознавание множества синонимов приветствий
- 🎭 Различные голоса (am_liam, af_heart и др.)
- 🚪 Команды для выхода
- 📦 Работает в Google Colab

## 🛠️ Установка и запуск

### 1. Установка зависимостей

```python
!pip install -q kokoro>=0.9.4 soundfile
!apt-get -qq -y install espeak-ng > /dev/null 2>&1

from kokoro import KPipeline
from IPython.display import Audio, display
import soundfile as sf
import time

pipeline = KPipeline(lang_code='a')

🎮 Доступные команды
Приветствия (будут распознаны автоматически):
hello, hello!, hello there

hi, heya

hey, hey there

good morning, morning, good day

good afternoon

good evening, evening

what's up, wassup, whassup

howdy, howdy there

greetings, greetings and salutations

yo, yo yo

sup, what's happening

hiya

how are you, how's it going

nice to meet you, how do you do, pleased to meet you

Команды выхода:
quit, exit, stop

goodbye, bye

пока

🎤 Доступные голоса
am_liam - основной мужской голос (по умолчанию)

af_heart - женский голос (используется для прощания)

Другие голоса Kokoro: af_bella, af_nicole, am_adam, am_michael и др

⚠️ Возможные проблемы и решения
Проблема: Лишние предупреждения (WARNING)
Решение: Это нормально - модель Kokoro загружается с настройками по умолчанию. Предупреждения не влияют на работу.

Проблема: Нет звука
Решение:

Убедитесь, что в Colab разрешен аудиовыход

Проверьте громкость в браузере

Перезапустите среду выполнения (Runtime → Restart runtime)

Проблема: Ошибка "pipeline not defined"
Решение: Все установки и импорты должны быть в одной ячейке или выполняться последовательно сверху вниз.

Проблема: Не распознает русские команды
Решение: Добавьте русские фразы в словарь responses вручную.
