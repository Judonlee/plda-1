# Probabilistic Linear Discriminant Analysis

### Disclaimer
This model was written for
 an [Explainable Artificial Intelligence (XAI) project](
     http://shaftolab.com/people.html), 
 so it stores a bunch of parameters in memory that 
 are not necessary for simple classification problems.

### Paper Citation
[Ioffe S. (2006) Probabilistic Linear Discriminant Analysis. 
 In: Leonardis A., Bischof H., Pinz A. (eds) Computer Vision – ECCV 2006. 
 ECCV 2006.](
 https://link.springer.com/chapter/10.1007/11744085_41)

### Dependencies
If you already have 
 [Anaconda or Miniconda](
  https://conda.io/docs/user-guide/install/index.html),
 you can automatically download all dependencies to a conda environment 
 called `plda` with the following. 

```conda env create -f environment.yml -n plda```

### Testing
If you created the Conda environment with the name `plda`, 
 activate it with the following.
``` shell
source activate plda
```

To run all tests (~120 seconds with ~60 CPU cores), use the following.
``` shell
python3.6 pytest plda/tests/
```

To run Run a particular test file, run one of the following
``` shell
pytest plda/tests/test_model/test_model_units.py  # ~.66s for me.
pytest plda/tests/test_model/test_model_integration.py  # ~1.0s for me.
pytest plda/tests/test_model/test_model_inference.py  #  ~80.6s for me.

pytest plda/tests/test_optimizer/test_optimizer_units.pa  # ~.59s for me..
pytest plda/tests/test_optimizer/test_optimizer_integration.py  # ~.78s.
pytest plda/tests/test_optimizer/test_optimizer_inference.py  # 25.3s for me.

python3.6 plda/tests/test_classifier/test_classifier_integration.py  #.69s.
```

Finally, 
 clean up the `__pycache__/` folders with the following.
``` shell
py3clean plda/
```

### Demo with MNIST Handwritten Digits Data
See [demos/mnist_data/mnist_demo.ipynb](
     ./demos/mnist_data/mnist_demo.ipynb).
- Although the model can automatically preprocess your data, 
   you should worry about overfitting when training on small datasets.
- One way to address this is to reduce the number of principal components 
   present in the preprocessed data.
- The MNIST demo shows that preprocessing is as simple as changing 
   an optional parameter.
