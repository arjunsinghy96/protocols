# Machine Translation (Text to Text)

## Goal

The goal of machine translation is to accurately and fluently translate text from one language to another while preserving the original meaning, context, tone, and cultural nuances.

## Evaluation

Responses will be evaluated by human reviewers for accuracy, fluency, and contextual fidelity. The translation should be precise, natural, and culturally appropriate, preserving the meaning and intent of the source text. Translations that deviate significantly from the source text, introduce inaccuracies, or fail to maintain linguistic and cultural integrity will receive lower scores.

Additional automated scoring criteria:

- BLEU (Bilingual Evaluation Understudy: (Measures the overlap between the machine translation output and reference translations)
- TER (Translation Edit Rate): (Evaluates the number of edits required to transform the machine translation into a reference translation)
- METEOR: (Considers precision, recall, and alignment to evaluate translation quality)
- CHR (Character-Level HTER) (Character-level translation edit rate)

## Actions

### `languages()`

- **Params**:
  - `api_version` (_string_, optional): The version of the API to be used.
- **Returns**:
  - **`languages`**: A list of supported languages for both language detection and translation.
    - **`language_code`** (_string_): A standardized code for the language (e.g., `en` for English, `es` for Spanish).
    - **`language_name`** (_string_): The full name of the language (e.g., "English," "Spanish").
  - Text must be UTF-8 encoded, under 1MB in size, and adhere to a margin of �10% for any word count constraints.

### `translate()`

- **Params**:
  - `source_text` (_string_): The text to be translated. Max 5000 words.
  - `source_language` (_string_): The language code of the source text. Optional if auto-detection is enabled.
  - `target_language` (_string_): The language code of the target translation.
  - `options` (_object_, optional): Additional parameters such as tone, formality, or domain specificity.
- **Returns**:
  - **`translated_text`** (_string_): The translated text in the target language, preserving meaning, tone, and context.

### `detectLanguage()`

- **Params**:
  - `text` (_string_): The text for which the language is to be detected.
- **Returns**:
  - **`detected_language`** (_object_):
    - **`language_code`** (_string_): The detected language code (e.g., `fr` for French).
    - **`confidence`** (_float_): The confidence level of the detected language (e.g., 0.98).

## Performance Requirements

- **Response Times**:
  - `translateText()`: Query response within 60 seconds.
  - `detectLanguage()`: Query response within 30 seconds.
- **Rate Limits**:
  - Minimum of 2 requests per minute.
  - At least 200 API calls per subscription per month.

## Constraints

- **Translation Accuracy**:
  - Translations must accurately preserve the original meaning and context of the source text.
- **Language Detection Reliability**:
  - Language detection should have a confidence level of at least 95% to be considered reliable.
- **Translation Quality**:
  - Translated text must be free from grammatical errors and adhere to cultural and contextual nuances of the target language.
