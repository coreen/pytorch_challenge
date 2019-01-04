# Udacity Intro to PyTorch Challenge

Final challenge for the [PyTorch Scholarship Challenge from Facebook](https://www.udacity.com/facebook-pytorch-scholarship). The challenge is to create a PyTorch image classifier from scratch that will identify different species of flowers.

![Scholarship Badge](https://github.com/coreen/pytorch_challenge/blob/master/ScholarshipBadge.png)

## Dataset

The provided dataset contains both a training and validation set. The zipped archive can be downloaded from https://s3.amazonaws.com/content.udacity-data.com/courses/nd188/flower_data.zip

## Steps to run

1. Download dataset from the link above to the top-level of the repository
2. Unzip by running `unzip flower_data.zip`
3. Run the Image Classifier Project.ipynb notebook using `jupyter notebook`

## Known Issues

When submitting the project, it was discovered that the Jupyter Notebook itself does not set a classifier when loading the `model_vgg19.pt` file in the `load_model` function. This should be updated to include the following snippet:

```
# Put the classifier on the pretrained network
model.classifier[6] = nn.Linear(4096, 102)
```

===============

Currently 2 files are generated when training and both need to be loaded for the model to be used. Ideally, both the `class_to_idx` and `state_dict` would be saved in the same file for a single load point.

