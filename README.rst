
.. raw:: html

	<p align="center">
		<img src="./logo/logo_lce.svg" width="35%">	
	</p>
	
	<div align="center">
		<a href="https://circleci.com/gh/LocalCascadeEnsemble/LCE/tree/main">
			<img src="https://circleci.com/gh/LocalCascadeEnsemble/LCE/tree/main.svg?style=shield">
		</a>
		<a href="https://codecov.io/gh/LocalCascadeEnsemble/LCE">
			<img src="https://codecov.io/gh/LocalCascadeEnsemble/LCE/branch/main/graph/badge.svg?token=VTA64P4GTF">
		</a>
		<a href="https://lce.readthedocs.io/en/latest/?badge=latest">
			<img src="https://readthedocs.org/projects/lce/badge/?version=latest">
		</a>
		<a href="https://pypi.python.org/pypi/lcensemble/">		
			<img src="https://badge.fury.io/py/lcensemble.svg">
		</a>		
		<a href="https://pypi.python.org/pypi/lcensemble/">		
			<img src="https://img.shields.io/pypi/pyversions/lcensemble.svg">
		</a>
		<a href="https://github.com/psf/black">	
			<img src="https://img.shields.io/badge/code%20style-black-000000.svg">
		</a>
		<a href="https://pypi.python.org/pypi/lcensemble/">		
			<img src="https://img.shields.io/github/license/LocalCascadeEnsemble/LCE.svg">
		</a>
	</div>
   
| **Local Cascade Ensemble (LCE)** is a *high-performing*, *scalable* and *user-friendly* machine learning method for the general tasks of **Classification** and **Regression**.
| In particular, LCE:
 
- Enhances the prediction performance of Random Forest and XGBoost by combining their strengths and adopting a complementary diversification approach
- Supports parallel processing to ensure scalability
- Handles missing data by design
- Adopts scikit-learn API for the ease of use
- Adheres to scikit-learn conventions to allow interaction with scikit-learn pipelines and model selection tools
- Is released in open source and commercially usable - Apache 2.0 license


Getting Started
===============

This section presents a quick start tutorial showing snippets for you to try out LCE.

Installation
------------

You can install LCE from `PyPI <https://pypi.org/project/lcensemble/>`_ with ``pip``::

	pip install lcensemble
	
Or ``conda``::

	conda install -c conda-forge lcensemble
	
	
First Example on Iris Dataset
-----------------------------

LCEClassifier accuracy on an Iris test set:

.. code-block:: python

	from lce import LCEClassifier
	from sklearn.datasets import load_iris
	from sklearn.metrics import accuracy_score
	from sklearn.model_selection import train_test_split


	# Load data and generate a train/test split
	data = load_iris()
	X_train, X_test, y_train, y_test = train_test_split(data.data, data.target, random_state=0)

	# Train LCEClassifier with default parameters
	clf = LCEClassifier(n_jobs=-1, random_state=0)
	clf.fit(X_train, y_train)

	# Make prediction and compute accuracy score
	y_pred = clf.predict(X_test)
	accuracy = accuracy_score(y_test, y_pred)
	print("Accuracy: {:.1f}%".format(accuracy*100))
	
.. code-block::
	
	Accuracy: 97.4%


Documentation
=============

LCE documentation, including API documentation and general examples, can be found `here <https://lce.readthedocs.io/en/latest/>`_.


Contribute to LCE
=================

Your valuable contribution will help make this package more powerful, and better for the community.
There are multiple ways to participate, check out this `page <https://lce.readthedocs.io/en/latest/contribute.html>`_!


Reference Papers
================

LCE originated from a research at `Inria, France <https://www.inria.fr/en>`_. 
Here are the reference papers:

.. [1] Fauvel, K., E. Fromont, V. Masson, P. Faverdin and A. Termier. LCE: An Augmented Combination of Bagging and Boosting in Python. arXiv, 2023

.. [2] Fauvel, K., E. Fromont, V. Masson, P. Faverdin and A. Termier. XEM: An Explainable-by-Design Ensemble Method for Multivariate Time Series Classification. Data Mining and Knowledge Discovery, 36(3):917–957, 2022

.. [3] Fauvel, K., V. Masson, E. Fromont, P. Faverdin and A. Termier. Towards Sustainable Dairy Management - A Machine Learning Enhanced Method for Estrus Detection. In Proceedings of the 25th ACM SIGKDD International Conference on Knowledge Discovery & Data Mining, 2019

If you use LCE, we would appreciate citations.


Contact
=======

If you have any question, you can contact me here: `Kevin Fauvel <https://www.linkedin.com/in/kevin-fauvel-phd-cfa-caia-51b7777a/>`_.