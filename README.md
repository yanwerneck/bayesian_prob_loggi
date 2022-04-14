
# Example of use for a beta modelling


```python
pip install bayesian-models-loggi
```


```python
from bayesian_models_loggi.beta import BetaBayes
```


```python
beta = BetaBayes(0.001, 0.001, 200, 400)
```


```python
beta.generate_posteriori_sample(name = "Control", sample_size = 100000)
```


```python
beta.plot()
```


```python
beta.generate_new_scenario(alpha_priori = 0.001, 
                           beta_priori = 0.001, 
                           success_count = 100, 
                           failure_count = 200, 
                           name = "Variant 1")
```


```python
beta.plot_scenarios()
```


```python
beta.generate_new_scenario(alpha_priori = 0.001, 
                           beta_priori = 0.001, 
                           success_count = 100, 
                           failure_count = 400, 
                           name = "Variant 2")
```


```python
beta.plot_scenarios()
```


```python
beta.prob_between_scenarios("Control", "Variant 1")
```


```python
beta.prob_lower_than_constant(0.8, "Variant 1")
```


```python

```


```python
beta.prob_lower_than_constant(0.35, "Control")
```


```python
beta.prob_lower_than_constant(0.35)
```