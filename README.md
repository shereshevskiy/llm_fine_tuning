# LLM Fine-Tuning Demo

Этот проект демонстрирует процесс файн-тюнинга больших языковых моделей (LLM) на Mac с процессорами M1/M2, включая использование PyTorch с поддержкой MPS (Metal Performance Shaders).

## Описание проекта

Проект предназначен для демонстрации файн-тюнинга open-source моделей, таких как LLaMA или Mistral. Он включает настройку среды, загрузку данных, процесс обучения с использованием метода LoRA, и тестирование результатов.

---

## Установка

Для воспроизведения проекта выполните следующие шаги:

### 1. Клонируйте репозиторий

git clone `<URL>`

cd <папка_проекта>

**2. Создайте виртуальное окружение**

python -m venv llm_env

source llm_env/bin/activate

**3. Установите PyTorch**

Установите PyTorch, оптимизированный для работы на процессорах Apple M1/M2:

./install_pytorch.sh

**	** **Примечание** : Убедитесь, что скрипт **install_pytorch.sh** имеет права на выполнение:

**4. Установите остальные зависимости**

pip install -r requirements.txt

**Проверка среды**

После установки выполните следующую команду, чтобы убедиться, что PyTorch настроен правильно:

**python -c **"import torch; print(torch.backends.mps.is_available())"

Если вывод **True**, PyTorch поддерживает ускорение через MPS на вашем устройстве.

**Запуск проекта**

**Настройка**

Если проект требует конфигурации (например, пути к данным), скопируйте файл **.env.example** и заполните его:

cp .env.example .env

**Запуск обучения**

Для запуска основного скрипта обучения выполните:

python main.py

Результаты обучения будут сохранены в папке **fine_tuned_model/**.

**Структура проекта**

llm_fine_tuning/

├── README.md **            **# Описание проекта

├── requirements.txt**      **# Зависимости (кроме PyTorch)

├── install_pytorch.sh**    **# Скрипт для установки PyTorch

├── main.py **              **# Основной код проекта

├── .env.example**          **# Пример конфигурационного файла

├── data/ **                **# Папка для данных

├── fine_tuned_model/ **    **# Выходная папка для обученной модели

**Пример данных**

Данные для обучения хранятся в папке **data** в формате JSONL. Пример файла:

**{**"instruction"**: **"Translate to French"**, **"input"**: **"Hello, world!"**, **"output"**: **"Bonjour, le monde!"**}**

**{**"instruction"**: **"Summarize"**, **"input"**: **"AI is transforming industries."**, **"output"**: **"AI revolutionizes industries."**}**

**Зависимости**

**Основные зависимости**

**	**•**	**transformers>=4.33.0

**	**•**	**datasets>=2.14.0

**	**•**	**peft>=0.4.0

**	**•**	**accelerate>=0.21.0

**Установка PyTorch**

PyTorch устанавливается через отдельный скрипт **install_pytorch.sh** с указанием оптимизированного индекса:

pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu

**Контакт**

Если у вас возникли вопросы или предложения, пишите на [email@example.com](mailto:email@example.com).

Этот `README.md` документирует весь процесс и позволяет другим легко воспроизвести ваш проект. Если что-то нужно улучшить, дайте знать! 😊