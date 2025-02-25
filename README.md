# ai-application-rag

## Project Description

This project helps medical professionals to find information on medications.

### Name & URL

| Name          | URL |
|---------------|-----|
| Huggingface (or streamlit)   | [Huggingface Space](https://huggingface.co/spaces/kuhs/ai-application-oxford-pets) |
| Embedding Model Page    | [Huggingface Model Page](https://huggingface.co/sentence-transformers/paraphrase-multilingual-mpnet-base-v2) |
| Code          | [GitHub Repository](https://github.com/Jasminh/ai-application-rag) |

## Data Sources

| Data Source | Description |
|-------------|-------------|
| [Compendium](https://compendium.ch/) | Swiss Drug Registry  |
| Other data | We also included data of the NHS |

## RAG Improvements

| Improvement                     | Description |
|-----------------------------------|-------------|
| `Query Expansion`          | Generate extra queries to expand search |
| `Query Rewriting`              | Rewrite queries to yield better result |
| `Result reranking` | Reranked the top 10 results with another model |

## Chunking

### Data Chunking Method

The data was chunked with the following logic to improve the performance of the RAG model:

| Type of Chunking  | Configuration |
|------------|---------------:|
| RecursiveCharacterTextsplitter      | 1000 characters, 100 overlap         |
| I also tried this method | x, y           |
| I also tried this one       | x, y           |

## Choice of LLM

| Name | Link | Validation Loss | Accuracy |
|-------|---------------|-----------------|----------|
| 1     | 0.373000      | 0.273244        | 93.37%   |
| 2     | 0.212700      | 0.214763        | 94.05%   |
| 3     | 0.180100      | 0.191792        | 94.45%   |
| 4     | 0.144800      | 0.185732        | 94.72%   |
| 5     | 0.130800      | 0.181368        | 94.45%   |

### TensorBoard

Details of training can be found at [Huggingface TensorBoard](https://huggingface.co/kuhs/vit-base-oxford-iiit-pets/tensorboard)

| Model/Method                                                         | TensorBoard Link                                      |
|----------------------------------------------------------------------|------------------------------------------------------|
| Transfer Learning with `google/vit-base-patch16-224` (without data augmentation) | runs/Feb07_17-31-08_clt-mob-w-2019                    |
| Transfer Learning with `google/vit-base-patch16-224` (with data augmentation)  | runs/Feb07_17-09-30_clt-mob-w-2019                    |

![alt text](doc/eval.png)

## Results

| Model/Method                                                         | Accuracy | Precision | Recall |
|----------------------------------------------------------------------|----------|-----------|--------|
| Transfer Learning with `google/vit-base-patch16-224` (without data augmentation) | 93%      | -         | -      |
| Transfer Learning with `google/vit-base-patch16-224` (with data augmentation)  | 95%      | -         | -      |
| Zero-shot Image Classification with `openai/clip-vit-large-patch14` | 88%      | 87.68%    | 88%    |

## References

![Class Distribution](doc/class_distribution.png)  
![Dog vs Cat](doc/dog_cat.png)  
![Sample Prediction (Transfer Learning)](doc/sample_prediction_transferlearning.png)
