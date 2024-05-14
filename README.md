# GeoQA-Plus
1. Download GeoQA+ benchmark [<a href="https://drive.google.com/file/d/1U0lEhr8v3khx-ukcZs92MvJqGQat7TBI/view?usp=drive_link">Google Drive</a>]
2. Download the GeoQA.rar(If it need permission please apply it through the Google drive link or contact this e-mail address to get it: jiecao@m.scnu.edu.cn, You can also contact this email address for any other issues), move it to GeoQA+/data/GeoQA2.2 path, and unzip it. GeoQA-train.pk is the training set of GeoQA, Mix-train.pk are the training set after mixing our newly annotated problems with GeoQA-train.pk，Backtrans-train.pk is the training set after performing data augmentation on Mix-train, new-test.pk is the test set formed by our new dataset. When using data files as training sets make sure to rename the corresponding data files to "train.pk".
3. Repalce the vocabulary file of Pre-training model with our "vocab.txt".
# Environment
pip install -r requirement.txt

# Train the model
cd GeoQA+

unzip and rename the dataset

run: allennlp train config/NGS_Aux.json --include-package NGS_Aux -s save/test

# Evaluation

run: allennlp evaluate save/test  data/GeoQA2.2/test.pk --include-package NGS_Aux_test --cuda-device 0
