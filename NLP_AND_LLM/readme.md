# Glossary of terms

Glossary of NLP and LLM Terms (With Examples)

Active Learning: A technique where the model identifies data samples it is uncertain about and requests human annotations to improve its performance
Example: Using active learning to label ambiguous customer feedback for better sentiment analysis

AI Agents: Autonomous systems powered by AI that can perform complex tasks by combining capabilities such as planning, decision-making, and learning
Example: An AI agent schedules meetings, responds to customer queries, and proactively follows up on pending tasks by integrating with calendars, CRMs, and other tools.

AI Safety: Research and practices aimed at ensuring AI systems are aligned with human values and avoid unintended consequences
Example: Developing methods to prevent LLMs from generating harmful or biased content

Agentic AI: A type of AI system designed to operate autonomously, with the ability to set and pursue goals, adapt to changing environments, and make decisions based on a combination of reasoning, learning, and external interactions
Example: An agentic AI monitors supply chain operations, identifies inefficiencies, and independently suggests or implements optimization strategies without requiring continuous human oversight.

Anomaly Detection: Identifying unusual patterns in data
Example: Detecting suspicious transactions in financial systems.

Artificial Intelligence (AI): The simulation of human intelligence by machines, enabling them to perform tasks such as learning, problem-solving, and decision-making
Example: AI algorithms recommend products to customers based on their browsing history.

Autoregressive Models: Models that generate text by predicting one token at a time based on the previously generated ones
Example: GPT models generate coherent text by predicting the next word sequentially.

Bias Mitigation: Efforts to reduce unintended biases in AI outputs
Example: Adjusting a recruitment model to avoid favoring candidates based on gender or ethnicity

Chatbots: AI-powered conversational agents that simulate human-like interactions
Example: A banking chatbot answers queries about account balances and recent transactions.

Compliance Automation: Applying NLP to ensure adherence to regulations
Example: An AI tool extracts and validates GDPR compliance clauses in contracts.

Context Window: The amount of text an LLM can consider when processing or generating a response
Example: An LLM with a context window of 4,000 tokens can analyze an entire legal contract for key clauses.

Corpus: A large and structured set of texts used for training and evaluating NLP models
Example: A corpus of news articles is used to train a language model for summarization tasks.

Data Augmentation: Techniques used to increase the size and diversity of training data, often by creating synthetic data or modifying existing data
Example: Generating variations of existing customer service conversations to improve the training of a chatbot.

Data Drift: A change in the statistical properties of input data over time, which can reduce model performance
Example: A sentiment analysis model trained on pre-pandemic customer feedback may perform poorly on post-pandemic data.

Deep Learning: A subset of ML that uses neural networks with multiple layers to model complex patterns
Example: Deep learning powers real-time language translation in Google Translate using recurrent neural networks (RNNs) and transformers.

Dialog Management: Systems that control the flow of conversation in chatbots or virtual assistants
Example: A chatbot managing turn-taking while helping users reset their passwords

Document Parsing: Using AI to extract structured information from unstructured text
Example: Parsing resumes to extract candidate skills, education, and experience

Embeddings: Numerical representations of text that capture semantic relationships
Example: "Bank" as a financial institution and "bank" as a riverbank are represented differently in context-sensitive embeddings.

Entity Extraction: The process of identifying and classifying named entities in text, such as names, dates, locations, and organizations
Example: Extracting "New York" and "July 4, 2025" from the sentence "The event is in New York on July 4, 2025."

Entity Linking: Connecting mentions of entities in text to a knowledge base
Example: Linking "Amazon" in a review to the e-commerce company, not the rainforest

Ethical AI: The practice of developing AI responsibly to avoid harm and promote fairness
Example: Implementing AI systems that explain their decisions to users transparently, considering data privacy, algorithmic bias, and responsible use of AI in decision-making

Explainability: The degree to which AI decisions and processes can be understood by humans
Example: An AI-generated loan approval decision that highlights key factors influencing the decision

Few-Shot Learning: Providing a few examples within the prompt to guide the model's task performance
Example: Showing examples of how to classify emails as "urgent" or "non-urgent" before asking the model to classify new ones

Fine-Tuning: Customizing an LLM for specific tasks by training it further on domain-specific data
Example: Training GPT to handle customer inquiries for a specific airline, leading to improved accuracy, reduced training time, and customization to specific industry jargon

Generative AI: AI that creates new content like text, images, or audio
Example: Using AI to generate personalized greeting cards based on customer preferences

Grounding: Connecting an LLM to external data sources or tools to enhance its accuracy and capabilities
Example: Linking an LLM to a company's knowledge base so it can provide accurate answers to customer questions

Hallucination (in LLMs): When an LLM generates incorrect or nonsensical information, often presented with confidence
Example: An LLM summarizing a financial report invents a non-existent merger.

Hyperparameters: Configurable parameters that govern the training process of machine learning models
Example: Setting the learning rate and batch size while fine-tuning a pre-trained model

Intent Recognition: Determining the user’s purpose or goal in a statement
Example: Recognizing "I’d like to return this product" as a return request

Knowledge Graph: A structured representation of facts and their relationships
Example: Google uses a knowledge graph to show related entities when you search for "Barack Obama."

Language Generation: The ability of an AI model to produce human-like text
Example: Writing blog posts or generating creative ad copy automatically

Language Modeling: The ability of AI to predict the next word or sequence in a sentence
Example: Autocomplete in email applications predicting "meeting" after typing "Let’s schedule a"

Language Understanding: An AI model's ability to comprehend text or speech and its meaning
Example: Identifying that "Can you book a flight for me?" is a request to perform an action

Large Language Models (LLMs): AI models trained on massive text datasets to perform tasks like language translation, summarization, and content generation
Example: OpenAI’s GPT generates product descriptions for e-commerce websites.

Loss Function: A mathematical function used to evaluate how well a model’s predictions align with the expected outputs
Example: Cross-entropy loss is used in classification tasks to measure prediction errors.

Lowercasing: Converting all characters in a text to lowercase to ensure uniformity and reduce case sensitivity in NLP tasks
Example: Converting "Stock Market" to "stock market" for consistent text processing

Machine Learning (ML): A method where machines learn patterns from data to improve their performance on tasks without explicit programming
Example: ML algorithms analyze customer purchase patterns to predict future buying behavior, detect fraud, personalize marketing campaigns, and predict customer churn.

Model Compression: Techniques to reduce the size of a model while retaining performance, making it deployable on resource-constrained devices
Example: Compressing a chatbot model for use on mobile devices

Multimodal AI: AI that integrates and processes multiple types of data, such as text, images, and video
Example: An AI system that analyzes customer complaints (text) and associated product photos (images)

Named Entity Recognition (NER): Identifies entities like names, dates, and organizations in text
Example: Extracting "Apple Inc." and "January 1, 2025" from the sentence, "Apple Inc. launched a new product on January 1, 2025"

Natural Language Processing (NLP): A branch of AI that enables machines to understand, interpret, and generate human language
Example: An email spam filter uses NLP to classify messages as spam or important.

Overfitting: When a model performs well on training data but poorly on unseen data because it has learned noise instead of patterns
Example: A sentiment model trained only on product reviews from one retailer fails on reviews from another retailer.

POS (Part-of-Speech) Tagging: Identifying the grammatical role of each word in a sentence, such as nouns, verbs, or adjectives
Example: In "The quick brown fox jumps over the lazy dog," POS tagging identifies "fox" as a noun and "jumps" as a verb.

Prompt Chaining: A technique where the output of one LLM prompt is used as the input for another, allowing for complex tasks to be broken down into steps
Example: Using one prompt to extract key information from a document and a second prompt to summarize that information.

Prompt Engineering: The art of crafting precise prompts to guide LLMs for optimal outputs
Example: Asking, "Summarize this article for a 10-year-old" ensures the summary is simple and clear.

Reinforcement Learning: A method where a model learns by receiving feedback based on its actions to maximize rewards
Example: Using reinforcement learning to optimize chatbot responses for better user engagement

Removing Stop Words: The process of filtering out common words that add little meaning to NLP tasks, such as "and," "is," or "the."
Example: In the sentence "The stock market is bullish," removing stop words leaves ["stock", "market", "bullish"].

Retrieval Augmented Generation (RAG): A method that combines information retrieval (finding relevant documents) with LLM generation to create more accurate and informative responses
Example: A customer service chatbot uses RAG to access product manuals and provide detailed troubleshooting steps.

Risk Management: Using AI to detect and mitigate risks in business processes
Example: NLP models scan contracts to identify non-standard clauses that pose financial risk.

Semantic Search: Searching for results based on meaning rather than keywords
Example: Searching "How to fix a printer?" and receiving results for troubleshooting printer issues, even if the exact words differ.

Sentiment Analysis: An NLP task to determine whether the sentiment expressed in text is positive, negative, or neutral
Example: Analyzing customer reviews to identify dissatisfaction with a product

Stemming or Lemmatization: Techniques used to reduce words to their root form.

Stemming: Strips suffixes, often creating truncated versions of words.
Example: "Running" becomes "run."

Lemmatization: Converts words to their base dictionary form.
Example: "Running" becomes "run" and "better" becomes "good."

Text Summarization: The process of condensing a lengthy text into a shorter version while retaining key information
Example: Summarizing a 20-page market research report into a one-page executive summary

Token Embeddings: Vector representations of tokens that capture semantic meaning in a way models can understand
Example: Word2Vec embeddings capture relationships like “king - man + woman = queen.”

Tokenization: The process of splitting text into smaller components like words or subwords for analysis
Example: Breaking "The stock market is bullish" into ["The", "stock", "market", "is", "bullish"] for processing.

Topic Modeling: Identifying themes or topics within a large collection of text
Example: Analyzing customer feedback to determine recurring issues like "delivery delays" or "product quality"

Training Data: The dataset used to teach an AI model; the quality and diversity of training data directly impact the model's performance.
Example: A customer service chatbot trained on FAQs and previous support tickets

Transfer Learning: Adapting a pre-trained model to new but related tasks
Example: Using an LLM trained on general English to analyze legal documents

Vector Database: Specialized databases for storing and querying embeddings efficiently
Example: Using a vector database to retrieve similar documents based on semantic embeddings

Weight Tuning: Adjusting the weights in a neural network to optimize model predictions during training
Example: Fine-tuning weights to improve sentiment detection accuracy on a custom dataset

Zero-Shot Learning: The capability of an AI model to handle new tasks without additional training
Example: An AI trained on general text successfully answering questions about a niche industry
