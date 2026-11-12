# LLM evaluation on Brazilian tax law questions

Notebooks and results from an experiment that measures how well 23 large language models answer
questions about Brazilian corporate tax law, and how well automatic metrics agree with an LLM judge.

Part of my master's research in Computer Science at the Federal University of Goiás (UFG).

## What is here

| Path | What it is |
|---|---|
| `1_llm_question_answering.ipynb` | Each model answers the 101 questions, given the related legal text as context |
| `2_llm_judgment_analysis.ipynb` | GPT-4o judges each generated answer against the official answer |
| `3_llm_metric_analysis.ipynb` | ROUGE, BLEU and BERTScore per model, accuracy from the judge, correlations (Pearson, Spearman, Kendall) and Bland-Altman plots |
| `result_question_answer_generation/` | One CSV per model with the generated answers (23 models) |
| `result_question_answer_llm_evaluation/` | The same answers with the GPT-4o verdict |
| `tax_law_brazil_cosit/` | The dataset: 101 questions with official answers and a corpus of 30 legal documents |

Models include Llama 2 and 3, Mistral and Mixtral, Qwen 1.5 and 2, Yi, Gemma, Vicuna, WizardLM,
SOLAR, Platypus2, OpenHermes, OpenChat and GPT-3.5 Turbo.

## Dataset

The questions come from the "Perguntas e Respostas da Pessoa Jurídica 2023" collection, published
by the General Coordination of Taxation (Cosit) of the Brazilian Federal Revenue Service. See
[`tax_law_brazil_cosit/README.md`](tax_law_brazil_cosit/README.md). The dataset also lives on its
own in the [`dataset`](https://github.com/joaopaulopresa/dataset) repository.

## Running

```bash
pip install -r requirements.txt
```

Fill in `.env` with `OPENAI_API_KEY` and `TOGETHER_API_KEY`, then run the notebooks in order.
Open models are called through the Together API; GPT models through the OpenAI API.
