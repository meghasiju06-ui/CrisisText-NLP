## Dataset

This project uses the **CrisisMMD (Crisis Multimodal Twitter Dataset)** for humanitarian information classification.

The dataset is included in this repository under the `dataset/` folder. Both the original ZIP archive and the extracted TSV files are provided.

### Dataset Splits

The dataset is divided into three parts:

- **Training set:** 13,608 records
- **Development set:** 2,237 records
- **Testing set:** 2,237 records

### Dataset Files

```text
dataset/
├── crisismmd_datasplit_all.zip
├── task_humanitarian_text_img_train.tsv
├── task_humanitarian_text_img_dev.tsv
└── task_humanitarian_text_img_test.tsv

### Dataset Fields

The dataset contains information such as:

event_name – Name of the crisis/disaster event
tweet_id – Unique tweet identifier
image_id – Image identifier
tweet_text – Text of the tweet
image – Image information
label – Original humanitarian label
label_text – Text-based label
label_image – Image-based label
label_text_image – Combined text-image label

For this project, the tweet text (tweet_text) and humanitarian category labels (label_text) are primarily used for NLP classification.

### Implementation

The project was developed and executed using Google Colab. The Python source code is provided in the source_code/ folder.
