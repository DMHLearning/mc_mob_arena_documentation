Чтобы у вас была база надо сделать 2 вещи: выучить язык и прогуляться по ссылкам. Оформлять/сдавать результаты не надо. Надо знать и что интересно/непонятно обсудить со мной.
## Выучить язык
 Чтобы разговаривать на одном языке определите ВСЕ термины, которые есть ниже. Можно использовать нейронки, но надо читать результаты. Термины+продукты+понятия надо знать, чтобы вы меня понимали.
## База
Transformer Architecture - Это архитектура, которая обрабатывает слова не по порядку, а все сразу, понимая связи между ними. Как если бы мы читали книгу, обращая внимание на все слова одновременно, а не построчно.
Tokens & Tokenization - Токенизация — это процесс разбивки текста на маленькие части (токены). Например, "привет!" → ["при", "вет", "!"]. Модель думает этими кусочками, а не целыми словами.
Context Window​ - "Объём оперативной памяти" модели. Это максимальное количество текста (в токенах), которое модель может "увидеть" за один раз. Как размер листа бумаги, на котором мы делаем заметки.
Embeddings - "Цифровые отпечатки" слов. Каждое слово превращается в набор чисел (вектор), который сохраняет его смысл в виде векторного представления. Близкие по смыслу слова имеют похожие "отпечатки".
## Training & Fine-Tuning Techniques
Pre-training - Модель учат на огромных объемах текста просто понимать язык, без конкретных задач. Предтренировка.
Fine-tuning​ - Берём готовую модель и доучиваем её для конкретной задачи (например, медицинские консультации или программирование).
PEFT (Parameter-Efficient Fine-Tuning)​ - Методы тонкой настройки, которые меняют только маленькую часть модели, а не всю её целиком. Дешево и эффективно, если мы хотим дополировать модель для каких-то задач, не меняя всю модель.
LoRA (Low-Rank Adaptation)​ - Конкретный метод PEFT, когда к модели добавляются маленькие "адаптеры", а не переучиваются все параметры. То есть, если мы добавляем новые данные, например за 2025 год, когда модель обладает данными до 2024 года.
QLoRA (Quantized LoRA)​ - LoRA, но с использованием сжатия данных, чтобы занимать ещё меньше памяти.
RLHF (Reinforcement Learning from Human Feedback)​ - Модель учат, показывая ей ответы и говоря "это хороший ответ, а это плохой", пока она не научится давать только хорошие.
RLAIF (Reinforcement Learning from AI Feedback)​ - То же, что RLHF, но "репетитором" выступает другая AI-модель, а не человек.
## Quantization Methods
Quantization​ - Преобразование чисел из высокоточных в менее точные, чтобы модель занимала меньше места и работала быстрее.
GGUF (GPT-Generated Unified Format)](https://www.e2enetworks.com/blog/which-quantization-method-is-best-for-you-gguf-gptq-or-awq​) - Формат для хранения сжатых моделей, который легко использовать на разных устройствах.
GPTQ (GPT Quantization)[](https://www.linkedin.com/pulse/demystifying-llm-quantization-gptq-awq-gguf-explained-xiao-fei-zhang-1lmbe)​  - Метод сжатия, который старается максимально сохранить качество модели после сжатия.
AWQ (Activation-Aware Weight Quantization)](https://www.linkedin.com/pulse/demystifying-llm-quantization-gptq-awq-gguf-explained-xiao-fei-zhang-1lmbe)​  - Метод сжатия, который оставляет самые важные параметры нетронутыми для лучшего качества.
## Inference & Sampling Parameters
**Temperature**[](https://codefinity.com/blog/Understanding-Temperature,-Top-k,-and-Top-p-Sampling-in-Generative-Models)​  - "Креативность" модели. Низкая температура — предсказуемые ответы, высокая — более случайные и креативные.
**Top-k Sampling**[](https://www.promptingguide.ai/introduction/settings)​   - Модель выбирает следующее слово только из K самых вероятных вариантов.
**Top-p (Nucleus Sampling)**[](https://promptengineering.org/prompt-engineering-with-temperature-and-top-p/)​  - Модель выбирает из такого количества вариантов, чтобы сумма их вероятностей не превышала P.
## Advanced Architectures
**Mixture of Experts (MoE)**[](https://pinggy.io/blog/what_is_mixture_of_experts_in_llm_models/)​  - "Команда специалистов". Вместо одной большой модели — несколько "экспертов", и для каждой задачи выбирается подходящий специалист.
**Mamba / State Space Models (SSMs)**[](https://shchegrikovich.substack.com/p/mamba-as-an-alternative-architecture)​   - "Эффективный обработчик длинных текстов". Новая архитектура, которая лучше работает с очень длинными документами.
**S4 (Structured State Space Sequence Model)**[](https://shchegrikovich.substack.com/p/mamba-as-an-alternative-architecture)​  - Одна из первых успешных архитектур state space моделей.
## Prompt Engineering Techniques
**Zero-shot Prompting**[](https://morsoftware.com/blog/prompt-engineering-techniques)​  - Даём задачу без примеров, надеясь, что модель поймёт что нужно.
**Few-shot Prompting**[](https://www.k2view.com/blog/prompt-engineering-techniques/)​  - Показываем несколько примеров "ввод-вывод", чтобы модель поняла паттерн.
**Chain-of-Thought (CoT) Prompting**[](https://gail.wharton.upenn.edu/research-and-insights/tech-report-chain-of-thought/)​  - Просим модель показывать ход мыслей, а не только конечный ответ.
**Self-Consistency**[](https://www.dataunboxed.io/blog/the-complete-guide-to-prompt-engineering-15-essential-techniques-for-2025)​  - Запускаем цепочку рассуждений несколько раз и выбираем самый частый ответ.
**ReAct (Reasoning + Acting)**[](https://react-lm.github.io/)​  - Модель сначала рассуждает, потом может использовать инструменты (калькулятор, поиск и т.д.)
**Meta Prompting**[](https://www.dataunboxed.io/blog/the-complete-guide-to-prompt-engineering-15-essential-techniques-for-2025)​  - Создание промптов, которые помогают генерировать другие хорошие промпты.
## Retrieval & Knowledge Enhancement
**RAG (Retrieval-Augmented Generation)**[](https://www.glean.com/blog/rag-retrieval-augmented-generation)​  - Модель сначала ищет информацию в базе знаний, потом генерирует ответ на её основе.
**Vector Databases**[](https://www.datacamp.com/blog/the-top-5-vector-databases)​  - "Базы смыслов". Хранят тексты как векторы (числовые представления), позволяя быстро находить семантически похожие тексты.
**Graph RAG**[](https://datanucleus.dev/rag-and-agentic-ai/what-is-rag-enterprise-guide-2025)​  - Использует графы связей между понятиями для более глубокого понимания контекста.
**Hybrid Search**[](https://datanucleus.dev/rag-and-agentic-ai/what-is-rag-enterprise-guide-2025)​  - Комбинирует семантический поиск (по смыслу) и ключевые слова для лучших результатов.
## Agent Systems & Workflows
**LLM Agents**[](https://blog.n8n.io/llm-agents/)​  - Программы на основе LLM, которые могут самостоятельно выполнять задачи, используя инструменты.
**Agentic Workflows**[](https://skywork.ai/blog/agentic-ai-examples-workflow-patterns-2025/)​  - Цепочки действий, где несколько AI-агентов работают вместе над сложной задачей.
**Tool Calling / Function Calling**[](https://xenoss.io/blog/langchain-langgraph-llamaindex-llm-frameworks)​  - "Использование инструментов". Способность AI вызывать внешние функции (калькулятор, API, поиск и т.д.).
## Multimodal Models
**Vision-Language Models (VLMs)**[](https://code-b.dev/blog/vision-llm)​  
**Multimodal Understanding**[](https://huggingface.co/blog/vlms-2025)​  
## Safety & Alignment
**Jailbreaking**[](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)​  
**Prompt Injection**[](https://www.rohan-paul.com/p/prompt-hacking-in-llms-2024-2025)​  
**Constitutional AI**[](https://hertzfelt.io/blog/constitutional-ai-and-ai-alignment-building-safe-and-controllable-systems)​  
**Red Teaming**[](https://hiddenlayer.com/innovation-hub/three-distinct-categories-of-ai-red-teaming/)​  
**Hallucination**[](https://arxiv.org/abs/2507.15903)​  
## Test-Time Compute & Reasoning
**Test-Time Compute**[](https://arxiv.org/html/2502.06807v1)​  
**Reasoning Models**[](https://arxiv.org/html/2501.02497v3)​  
## Frameworks & Infrastructure
**LangChain**[](https://blog.langchain.com/langchain-langgraph-1dot0/)​  
**LangGraph**[](https://dev.to/clickit_devops/langchain-vs-langgraph-which-llm-framework-should-you-use-2k1p)​  
**vLLM**[](https://dev.to/mechcloud_academy/ollama-vs-vllm-a-detailed-comparison-of-llm-frameworks-513m)​  
**Ollama**[](https://www.hyperbolic.ai/blog/llm-serving-frameworks)​  
**OpenRouter**[](https://skywork.ai/blog/openrouter-review-2025/)​​  
**LiteLLM**[](https://www.litellm.ai/)​  
## Evaluation & Benchmarks
**MMLU (Massive Multitask Language Understanding)**[](https://github.com/leobeeson/llm_benchmarks)​  
**HumanEval**[](https://www.confident-ai.com/blog/llm-benchmarks-mmlu-hellaswag-and-beyond)​  
**BIG-Bench Hard (BBH)**[](https://www.confident-ai.com/blog/llm-benchmarks-mmlu-hellaswag-and-beyond)​  
**Chatbot Arena**[](https://www.confident-ai.com/blog/llm-benchmarks-mmlu-hellaswag-and-beyond)​  
**TruthfulQA**[](https://www.confident-ai.com/blog/llm-benchmarks-mmlu-hellaswag-and-beyond)​  
**MT-Bench**[](https://www.confident-ai.com/blog/llm-benchmarks-mmlu-hellaswag-and-beyond)​  
## Модели​
- **GPT-5** (OpenAI, August 2025): Unified multimodal model with 400K context, advanced reasoning    
- **Claude 4.1 Opus** (Anthropic, August 2025): 74.5% on SWE-bench, 200K context expanded to 1M + **4.5 Sonnet **   
- **Gemini 2.5 Pro** (Google, March 2025): 2M context window, "Deep Think" mode, multimodal    
- **Grok 4** (xAI, July 2025): 256K context, real-time X/Twitter data access    
- **Llama 4** (Meta, April 2025): Scout (17B, 10M context), Maverick (multimodal), MoE architecture    
- **Qwen3** (Alibaba, April 2025): 235B parameters, 258K native context (extendable to 1M)    
- **DeepSeek-V3/R1** (January 2025): 671B parameters (37B active), MoE, open-source reasoning model
## Остальное
**System-1 vs System-2 Thinking**[](https://www.ruxu.dev/articles/ai/test-time-compute/)​  
**Agentic E-commerce**[Referenced but details in ecosystem]  
**Thinking Budget / Extended Thinking**[](https://alphacorp.ai/top-5-llms-for-november-2025/)​  
**Prefix Caching**[](https://northflank.com/blog/vllm-vs-ollama-and-how-to-run-them)​  
**Serverless LLM Inference**  
**Long-context Benchmarks**[](https://epoch.ai/data-insights/context-windows)​  
## **Additional Terms for Russian Language Support**
Оставил тут определения, так как это чуть более узкая тема.

**Tokenization Efficiency for Cyrillic Scripts**[](https://arxiv.org/abs/2312.02598)​  
The performance degradation of Western LLMs when processing Russian and other Cyrillic languages due to inefficient tokenization. English-centric tokenizers like GPT-2's BPE often require 2-3x more tokens for Russian text compared to English, increasing costs and reducing context window effectiveness. Cyrillic characters are encoded as 2-byte UTF-8 sequences, and models without proper Cyrillic vocabulary representation break words into meaningless fragments.[](https://www.frontiersin.org/journals/artificial-intelligence/articles/10.3389/frai.2025.1538165/full)​

**Characters Per Token (CPT) / Bytes Per Token (BPT)**[](https://www.frontiersin.org/journals/artificial-intelligence/articles/10.3389/frai.2025.1538165/full)​  
Metrics measuring tokenization efficiency across languages. Lower CPT/BPT values indicate inefficient tokenization where meaningful linguistic units are split. For Russian, GPT-2 achieves ~2.5 CPT vs. specialized Russian tokenizers achieving ~4-5 CPT, directly impacting inference cost and context utilization.[](https://www.frontiersin.org/journals/artificial-intelligence/articles/10.3389/frai.2025.1538165/full)​

**Vocabulary Substitution / Tokenizer Adaptation**[](https://arxiv.org/html/2312.02598v1)​  
The process of replacing an LLM's original vocabulary with a new tokenizer trained on target language corpus (e.g., Russian), then reinitializing embeddings and continuing pre-training. Critical steps include: (1) building new vocabulary on Russian corpus, (2) rebuilding embedding layers, (3) initializing via overlap mapping, (4) continued pre-training on Russian text while often freezing most model weights.[](https://arxiv.org/abs/2312.02598)​

**BPE (Byte-Pair Encoding) vs. Unigram Tokenization**[](https://arxiv.org/html/2411.17669v1)​  
Two competing subword tokenization algorithms. BPE iteratively merges frequent character pairs, while Unigram starts with large vocabulary and prunes based on likelihood. For Russian adaptation, research shows Unigram achieves better morphological accuracy and token efficiency than BPE due to Russian's complex morphology (cases, aspects, conjugations).[](https://arxiv.org/html/2312.02598v1)​

**SentencePiece**[](https://www.reddit.com/r/MachineLearning/comments/rprmq3/d_sentencepiece_wordpiece_bpe_which_tokenizer_is/)​  
A language-agnostic tokenizer that treats text as raw byte streams without requiring pre-tokenization (whitespace splitting). Particularly useful for languages without clear word boundaries and for ensuring consistent tokenization across languages. Supports both BPE and Unigram algorithms, making it popular for multilingual models.[](https://arxiv.org/html/2411.17669v1)​

**Morphological Tokenization**[](https://eventiotic.com/eventiotic/files/Papers/URL/f09c4e20-75f0-4145-a224-2b30a460f885.pdf)​  
Tokenization that respects linguistic morphology (prefixes, roots, suffixes). Critical for morphologically rich languages like Russian where a single word can have 20+ inflected forms. English-centric tokenizers often split Russian words mid-morpheme, destroying semantic meaning.[](https://eventiotic.com/eventiotic/files/Papers/URL/f09c4e20-75f0-4145-a224-2b30a460f885.pdf)​

**Embedding Initialization Strategies**[](https://jle.hse.ru/article/download/22224/20341)​  
Methods for initializing new token embeddings when adapting vocabulary: (1) **Focus-based**: averaging embeddings of old tokens that overlap with new token, (2) **Distribution matching**: initializing based on statistical properties of similar tokens. Poor initialization can cause the model to "forget" how to use new tokens and revert to old, inefficient ones.[](https://jle.hse.ru/article/download/22224/20341)​

---

## **Russian LLM Ecosystem (November 2025)**
**YandexGPT 4/5 Pro**[](https://www.businessinsider.com/us-china-compete-ai-dominance-while-russia-model-lags-behind-2025-2)​  [](https://yandex.cloud/en/services/yandexgpt)​
**GigaChat Family (Sber)**[](https://arxiv.org/html/2506.09440v1)​  
**Vikhr (Open-Source Bilingual Russian LLM)**[](https://aclanthology.org/2024.mrl-1.15.pdf)​  
​**Russian Super GLUE Benchmark**[](https://arxiv.org/html/2312.02598v1)​  
​**Russian LLM Arena**[](https://www.businessinsider.com/us-china-compete-ai-dominance-while-russia-model-lags-behind-2025-2)​  
​
## **Multilingual & Cross-Lingual Concepts**
Аналогично
**Language Bias / English Dominance**[](https://arxiv.org/abs/2312.02598)​  
The systematic advantage English has in LLM training due to massive overrepresentation in pre-training datasets. Common pre-training corpora are 90%+ English, causing models to develop English-specific inductive biases that harm performance on morphologically complex languages like Russian, leading to "knowledge starvation" for non-English domains.[](https://arxiv.org/abs/2312.02598)​

**Cross-Lingual Transfer**[](https://jle.hse.ru/article/download/22224/20341)​  
The ability of multilingual models to transfer knowledge learned in high-resource languages (English) to low-resource languages (e.g., Russian). Effectiveness depends heavily on tokenization efficiency—poor Russian tokenization blocks transfer even when model has universal semantic representations.[](https://jle.hse.ru/article/download/22224/20341)​

**Language-Specific Fine-Tuning vs. Adapter-Based Approaches**[](https://arxiv.org/html/2405.13929v3)​  
Two strategies for Russian adaptation: (1) **Full fine-tuning**: updating all model weights with continued pre-training on Russian text (Vikhr approach), (2) **Adapter-based**: adding LoRA/QLoRA layers on top of frozen English model (cheaper but lower performance). Full approach requires more compute but achieves better Russian fluency and cultural understanding.[](https://arxiv.org/abs/2405.13929)​

**Continual Pre-Training / Post-Pretraining**[](https://aclanthology.org/2025.wmt-1.50.pdf)​  
Additional pre-training phase after initial training on massive multilingual corpus, focused on specific language(s) or domains. For Russian adaptation, involves training on Russian-English parallel corpora and monolingual Russian text to strengthen language-specific representations before instruction tuning.[](https://aclanthology.org/2025.wmt-1.50.pdf)​

# Прогуляться по ссылкам

## **Обоснование методики

Это задание построено по принципу Элодина из книг  Ротфусса. Суть не в конкретной ссылке, суть в охоте за знаниями. Чем больше поохотитесь, тем больше будете знать.
## Почему это работает для изучения LLM

Область больших языковых моделей в 2025 году:﻿

- **Противоречивая организация**: разные источники описывают одни и те же концепции с разных точек зрения. Один говорит, что Chain-of-Thought необходим для рассуждений; другой утверждает, что для o1/o3 он бесполезен. Оба правы в своём контексте.﻿
    
- **Бешеный темп изменений**: статья трёхмесячной давности может быть уже устаревшей. DeepSeek-R1 вышел в январе 2025 года и перевернул представления о стоимости обучения моделей рассуждения.﻿
    
- **Разнородные жанры знания**: вам нужно понимать и математику трансформеров, и политику албанского правительства (AI-министр Диелла), и экономику токенизации кириллицы, и философию безопасности ИИ (Constitutional AI). Все они связаны, но неочевидным образом.﻿
    
- **Невозможность «знать всё»**: даже исследователи в ведущих лабораториях не читали все статьи. Ключевой навык — научиться ориентироваться в потоке информации, доверять интуиции, следовать цитатам и принимать частичное понимание как норму.﻿
    

Это задание учит вас **не конкретным фактам**, а **способу мышления исследователя LLM**: способности синтезировать информацию из разнородных источников, находить паттерны в хаосе, различать фундаментальные концепции и временные тренды, и — самое важное — оставаться любопытными и открытыми к неожиданным связям.﻿

## Философия задания

Перед началом важно понять:﻿

1. **Нет единственного «правильного» источника**. Разные ресурсы освещают разные грани LLM-знаний. Техническая статья на arXiv даст вам математическую строгость. YouTube-разбор Yannic Kilcher — интуитивное понимание. Блог о Диелле — критическое мышление о применении ИИ. Все они ценны.﻿    
2. **Блуждание — это суть процесса**. Следовать цитатам и ссылкам не только разрешено, но и приветствуется. Уход в «боковую тропу» часто приводит к более глубокому пониманию.﻿  Формальное нажатие по 6 ссылкам ни к чему не приводит и только тратит время и электроэнергию.  
3. **Контекст важнее полноты**. Понимание того, _как_ инструменты связаны друг с другом, ценнее запоминания каждой детали.﻿    
4. **Вы будете не соглашаться с источниками**. Это данные, а не провал. Задокументируйте разногласия — они показывают, что вы думаете критически.﻿    
5. **Путаница и тупики ожидаемы**. Некоторые статьи будут слишком сложными. Некоторые YouTube-видео предполагают знания, которых у вас нет. Это нормально. Запишите, что было непонятно, и двигайтесь дальше. Понимание придёт через накопление опыта, а не через линейное изучение.﻿
    
## Инструкции

Вам предоставлен список из 25 конкретных ресурсов, разделённых на пять категорий:﻿

- **Категория A**: Архитектурные глубокие погружения (теория и механизмы)﻿    
- **Категория B**: Инструменты экосистемы и практическая инфраструктура﻿    
- **Категория C**: Передовые тренды и новые исследования﻿    
- **Категория D**: Безопасность, оценка и методология﻿    
- **Категория E**: Русский язык и токенизация﻿    

**Выберите хотя бы 6 элементов** из списка 25. Если хотите много знать, можете по всем 25 пройти. Ограничения:﻿

- Желательно минимум один из каждой категории (A, B, C, D, E)﻿    
- Путаница и тупики ожидаемы — задокументируйте их﻿
 
## Что делать с каждым найденным ресурсом

Для каждого из 6 выбранных элементов:﻿

1. **Найдите его**. Используйте Google Scholar, arXiv, YouTube, GitHub, Perplexity, официальные документации. Если ссылка не работает, ищите через название и авторов.﻿
    
2. **Прочитайте/посмотрите частично**. Вам НЕ нужно читать всю 50-страничную статью. Прочитайте аннотацию, введение, пролистайте методологию, изучите результаты. Для видео — посмотрите 5-10 минут, поймите главную мысль.﻿
    
3. **Запишите/запомните/осознайте**:﻿    
    - Одно предложение о том, **что** это за ресурс﻿        
    - Одну идею, которую вы **поняли**        
    - Одну вещь, которая осталась **непонятной**        
    - Одну связь с **другим** ресурсом из вашего списка (или с темой вашего проекта)﻿
        
4. **Следуйте одной цитате**. Если статья ссылается на другую работу, которая кажется интересной — откройте её. Если YouTube-видео упоминает статью — найдите её. 
5. **Найти что-нибудь интересное**. Плостно изучить и рассказать мне. Может быть исходый материал, может быть что-то связанное.

## **Category A: Architectural Deep Dives** (Theory & Mechanisms)

**1. "FlashAttention-3: Fast and Accurate Attention with Asynchrony and Low-Precision" (Dao et al., arXiv 2024)**[](https://arxiv.org/abs/2407.08608)​  
Find the paper on arXiv. Understand what "asynchronous warp-level pipelining" means for GPU memory efficiency. Why does this matter for long-context LLMs? Bonus: Find Tri Dao's blog post explaining it in simpler terms.[](https://pytorch.org/blog/flashattention-3/)​

**2. "Mamba-2: State Space Duality" (Gu & Dao, 2024)**[](https://goombalab.github.io/blog/2024/mamba2-part1-model/)​  
The Goomba Lab blog has a two-part series breaking down how Mamba-2 achieves O(N) complexity without attention. Read Part I (the model) or Part II (the theory). What is "semiseparable matrix structure" and why does it challenge transformer dominance?[](https://tridao.me/blog/2024/mamba2-part2-theory/)​

**3. OpenAI o1 System Card (September 2024) + Wikipedia Article[](https://en.wikipedia.org/wiki/OpenAI_o1)​  
Read OpenAI's official o1 system card about "thinking time" and test-time compute. Then find the Reddit discussion or research paper claiming o1 demonstrates "true reasoning" vs. memorization. Where do they disagree?[](https://www.reddit.com/r/OpenAI/comments/1h9l4jx/paper_shows_o1_demonstrates_true_reasoning/)​

**4. "Constitutional AI: Harmlessness from AI Feedback" (Bai et al., Anthropic 2022)**[](https://arxiv.org/pdf/2212.08073.pdf)​  
The original Constitutional AI paper (PDF). Read sections 1-3. How does "AI critiquing AI" differ from RLHF? Find one blog post or tweet criticizing this approach—what's the counterargument?[](https://www-cdn.anthropic.com/7512771452629584566b6303311496c262da1006/Anthropic_ConstitutionalAI_v2.pdf)​

**5. DeepSeek-R1 Technical Report (January 2025)**[](https://arxiv.org/pdf/2501.12948.pdf)​  
DeepSeek released their reasoning model with pure RL—no supervised fine-tuning first. Read the GitHub README and skim the paper's "RL without SFT" section. How did they achieve 97.3% on MATH-500? What does "two-stage RL pipeline" mean?[](https://github.com/deepseek-ai/DeepSeek-R1)​

---
## **Category B: Ecosystem Tools & Practical Infrastructure**

**6. Diella: Albania's AI Minister (September 2025)**[](https://www.euronews.com/next/2025/10/30/albanias-ai-minister-is-pregnant-with-83-digital-assistants-prime-minister-says)​  
Read at least three articles about Albania appointing "Diella," an AI system, as Minister of Public Procurement. Find the Euronews article, the Forbes analysis, and one critical piece. What problem is Prime Minister Edi Rama trying to solve? Is Diella actually making decisions or is this political theater? What are the cybersecurity risks?[](https://gfmag.com/economics-policy-regulation/albania-ai-chatbot-minister-joins-government/)​

**7. LangGraph Documentation: "Building Agentic Workflows"**[](https://www.ibm.com/think/tutorials/build-agentic-workflows-langgraph-granite)​  
Navigate to LangGraph's official docs (or the IBM tutorial on LangGraph + Granite). Understand what "stateful graphs" and "nodes as agents" mean. How is LangGraph different from basic LangChain chains? Find one real-world use case example.[](https://docs.langchain.com/oss/python/langgraph/workflows-agents)​

**8. Claude 3.5 Computer Use API Documentation + Case Study Paper (arXiv 2411.10323)**[](https://arxiv.org/html/2411.10323v1)​  
Read Anthropic's announcement of "computer use" capability. Then find the arXiv case study testing Claude's ability to control desktop GUIs. What tasks did Claude succeed/fail at? What are the safety implications of AI controlling your computer?[](https://www.anthropic.com/news/3-5-models-and-computer-use)​

**9. vLLM vs. Ollama: Performance Benchmarking Blog**[](https://dev.to/mechcloud_academy/ollama-vs-vllm-a-detailed-comparison-of-llm-frameworks-513m)​  
Find a detailed comparison post (Red Hat's deep dive, Northflank's guide, or the "Definitive Guide" blog). What is PagedAttention? When would you use Ollama over vLLM? Create a simple decision tree for choosing between them.[](https://northflank.com/blog/vllm-vs-ollama-and-how-to-run-them)​

**10. OpenRouter Documentation: "Getting Started" + Pricing Page**[](https://skywork.ai/blog/openrouter-review-2025/)​  
Explore OpenRouter's docs and model catalog. It aggregates 400+ models—why does this matter? Find the pricing comparison for GPT-4, Claude 3.5, and Llama 4. What is "smart routing" and how does it save costs?[](https://openrouter.ai/docs/faq)​

---
## **Category C: Frontier Trends & Emerging Research**

**11. "Awesome-LLM-Long-Context-Modeling" GitHub Repository**[](https://github.com/Xnhyacinth/Awesome-LLM-Long-Context-Modeling)​  
Browse this curated list of papers on context length optimization. Pick one paper title that intrigues you (e.g., "Infinite Attention," "YARN," "LongLoRA"). Read its abstract. What technique does it use to extend context beyond the training window?[](https://github.com/Xnhyacinth/Awesome-LLM-Long-Context-Modeling)​

**12. Sebastian Raschka's "LLM Research Papers: 2025 List (January-June)"**[](https://magazine.sebastianraschka.com/p/llm-research-papers-2025-list-one)​  
Navigate to his Substack and find the curated list of 200+ papers. Pick one from the "Test-Time Compute" or "Reasoning Models" section (post-October 2025). Why did Sebastian think this paper mattered? What's one sentence you understood and one you didn't?[](https://www.llmsresearch.com/p/llm-research-highlights-march-1-15-2025-part1)​

**13. Trelis Research: "MCP Agent Fine-Tuning Workshop" (YouTube)**​  
Find Ronan McGovern's Trelis Research channel. Watch the workshop on Model Context Protocol (MCP) and agent fine-tuning. What is MCP? How does it differ from traditional function calling? Bonus: What's the business model for agent fine-tuning services?​

**14. "DeepSeek: Security, Privacy, and Governance—Hidden Risks in Open-Source AI" (Blog)**[](https://theori.io/blog/deepseek-security-privacy-and-governance-hidden-risks-in-open-source-ai)​  
Find one critical analysis of DeepSeek's open-source strategy (Theori.io's security analysis or Clausey.ai's monopoly-breaking piece). What are the governance risks of releasing frontier models with full weights? How does this differ from OpenAI's approach?[](https://www.clausey.ai/blogs/deepseek-reshaping-open-source-strategy)​

**15. Yannic Kilcher: "The Free Transformer" Paper Analysis (YouTube, October 2025)**[](https://www.ykilcher.com/)​​  
Search Yannic Kilcher's channel for his breakdown of "The Free Transformer" paper. What efficiency innovation does this paper propose? Why does Yannic find it interesting (or not)? What's one concept he explains that the paper abstract skipped?​[](https://www.ykilcher.com/)​

---
## **Category D: Safety, Evaluation & Methodology**

**16. OWASP Gen AI Security Top 10: "LLM01:2025 Prompt Injection"**[](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)​  
Read the OWASP documentation for the #1 LLM risk. Then find Microsoft's blog post "How Microsoft Defends Against Indirect Prompt Injection Attacks" (July 2025). What defense techniques do they recommend? Design one attack scenario and one mitigation.[](https://arxiv.org/html/2507.07974v1)​

**17. "Zero-Knowledge LLM Hallucination Detection and Mitigation" (EMNLP 2025)**[](https://aclanthology.org/2025.emnlp-industry.139.pdf)​  
Find the paper or Amazon Science blog post. What does "zero-knowledge" mean in this context? How do they detect hallucinations using cross-model consistency without access to ground truth? What's the key limitation?[](https://www.amazon.science/publications/zero-knowledge-llm-hallucination-detection-and-mitigation-through-fine-grained-cross-model-consistency)​

**18. Chain-of-Thought vs. Test-Time Compute: "The Decreasing Value of Chain of Thought" (Wharton, June 2025)**[](https://gail.wharton.upenn.edu/research-and-insights/tech-report-chain-of-thought/)​  
Find this paper (arXiv 2506.07142). The claim: CoT prompting matters less for o1/Claude 4-style reasoning models. Why? How does this change prompt engineering best practices for 2025? Find one rebuttal or counterexample.[](https://arxiv.org/abs/2506.07142)​

**19. LLM Benchmarks Explainer: MMLU, HumanEval, and BBH**[](https://github.com/leobeeson/llm_benchmarks)​  
Read one comprehensive guide (Confident AI, EvidentlyAI, or DataCamp). Pick two benchmarks and explain: What do they measure? Why do they matter? Find one criticism of benchmark gaming or overfitting.[](https://orq.ai/blog/llm-benchmarks)​

**20. AI Red Teaming: Anthropic's "Frontier Threats Red Teaming for AI Safety"**[](https://hertzfelt.io/blog/constitutional-ai-and-ai-alignment-building-safe-and-controllable-systems)​  
Read Anthropic's blog post (2023) or the HiddenLayer article on AI red teaming categories (2025). What is red teaming? How does it differ from traditional pentesting? Find one specific jailbreak technique and explain how it works.[](https://hiddenlayer.com/innovation-hub/three-distinct-categories-of-ai-red-teaming/)

## **Category E: Russian Language & Tokenization Deep Dives**

**21. "Impact of Tokenization on LLaMa Russian Adaptation" (Tikhomirov & Chernyshev, arXiv 2023)**[](https://arxiv.org/abs/2312.02598)​  
Find this paper on arXiv (2312.02598). Read sections on vocabulary substitution and embedding initialization strategies. Why does inefficient tokenization cause Russian instruction-tuning to fail? Compare BPE vs. Unigram results on Russian Super GLUE. What does "morphological accuracy" mean for tokenization?[](https://arxiv.org/html/2312.02598v1)​

**22. "Vikhr: Constructing a State-of-the-art Bilingual Open-Source Instruction-Following LLM" (arXiv 2024)**[](https://aclanthology.org/2024.mrl-1.15.pdf)​  
Read the Vikhr paper (arXiv 2405.13929). How did they adapt Mistral's tokenizer for Russian? Why did they choose full weight fine-tuning over LoRA adapters? Compare their approach to Saiga-Mistral or other Russian LLM attempts. What benchmarks did they use to prove Russian improvement?[](https://arxiv.org/html/2405.13929v3)​

**23. "GigaChat Family: Efficient Russian Language Modeling Through MoE" (arXiv 2025)**[](https://arxiv.org/html/2506.09440v1)​  
Find the GigaChat technical paper. They claim to be "the only model developed from scratch for Russian." What advantages does training from scratch give vs. adapting English models? How does their specialized tokenizer differ from GPT-2's? Why is GigaChat still ranked lower than Claude/ChatGPT on Russian tasks despite being "Russian-native"?[](https://arxiv.org/html/2506.09440v1)​

**24. YandexGPT WMT25 Translation Task Submission Paper (November 2025)**[](https://aclanthology.org/2025.wmt-1.50.pdf)​  
Search for "Yandex Submission to the WMT25 General Machine Translation Task" (ACL Anthology). This describes YandexGPT's architecture and training pipeline for Russian-English translation. What is "P-Tuning"? What does "curriculum learning with difficulty schedule" mean for alignment? How do they handle document-level context vs. sentence-level?[](https://aclanthology.org/2025.wmt-1.50.pdf)​

**25. Tokenization Efficiency Comparison: Frontiers in AI (August 2025)**[](https://www.frontiersin.org/journals/artificial-intelligence/articles/10.3389/frai.2025.1538165/full)​  
Find "Tokenization efficiency of current foundational large language models for Cyrillic languages" (Frontiers in Artificial Intelligence). Study their CPT/BPT metrics across GPT-4, LLaMA, and Russian-specialized models. Create a table: How many tokens does each model need for the same Russian sentence? What's the cost implication? Why does this matter for context windows?[](https://www.frontiersin.org/journals/artificial-intelligence/articles/10.3389/frai.2025.1538165/full)​​
## Дополнительное задание для работающих с русским языком

**Анализ токенизации**: Возьмите одно русское предложение (20-30 слов). Токенизируйте его с помощью:﻿
- Токенизатора GPT-2 (через HuggingFace)﻿    
- Токенизатора LLaMA﻿    
- Специализированного русского токенизатора (Vikhr или YandexGPT, если доступен)﻿    

Сравните: количество токенов, осмысленность разбиения, последствия для стоимости.