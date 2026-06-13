## 📁 Dataset & Notebook Setup

This project was developed using **Google Colab**.

The dataset file is not included in this repository because of its large size.
To run this project, please download the dataset from Kaggle:

[Big Five Personality Test Dataset](https://www.kaggle.com/datasets/tunguz/big-five-personality-test)

After downloading the dataset, place the file `data-final.csv` in your own project directory.

In this project, the dataset was loaded from Google Drive using this path:

```python
df = pd.read_csv(
    "/content/drive/MyDrive/ColabNotebooks/PersonaCluster/input/data-final.csv",
    sep="\t"
)
```

If you want to run the notebook on your own system, Google Colab, or Kaggle, you only need to change the dataset path.

For example:

```python
df = pd.read_csv("your_dataset_path/data-final.csv", sep="\t")
```

For Kaggle Notebook, the path may look like this:

```python
df = pd.read_csv("/kaggle/input/big-five-personality-test/data-final.csv", sep="\t")
```

---

## 🔄 Using a Different Dataset

You can also use another Big Five personality dataset, but it should have the same question structure.

The dataset should contain these columns:

* `EXT1` to `EXT10`
* `EST1` to `EST10`
* `AGR1` to `AGR10`
* `CSN1` to `CSN10`
* `OPN1` to `OPN10`

Each answer should be a number from **1 to 5**.

If your dataset has different column names, you must update the column selection part of the notebook before running the models.

Response time columns such as `EXT1_E`, `AGR2_E`, and similar columns are optional.
If they are not available, the response time cleaning step can be skipped.
