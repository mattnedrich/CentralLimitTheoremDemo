## Central Limit Theorem Demo
This project demonstrates the principles of the Central Limit Theorem by sampling a given input distribution 1000 times with a user specified sample size.

## Requirements
If plotting is enabled, [Matplotlib](http://matplotlib.org/) and [Seaborn](http://stanford.edu/~mwaskom/software/seaborn/) are required.

## Usage
The `central_limit_theorem_demo.py` file contains a `CentralLimitTheorem` class. It can be instantiated with a distribution in the form of a list.

```python
import central_limit_theorem_demo as clt

some_distribution = create_distribution(...)
cltDemo = clt.CentralLimitTheorem(some_distribution)
```

The demo can be run via the `run_sample_demo` method on CentralLimitTheoremDemo. This method takes a sample size `N`, a plotting flag `plot`, and an optional `num_bins` parameter describing the number of bins to use when plotting the demo output.

## Example
A full example might look something like this.

```python
import central_limit_theorem_demo as clt

def create_uniform_sample_distribution():
    return range(100)

def run():
    sampleDistribution = create_uniform_sample_distribution()
        
    # Plot the original population distribution
    clt.plot_distribution(sampleDistribution, "Population Distribution", 0, 100, 20)
        
    # Plot a sampling distribution for values of N = 2, 3, 10, and 30
    cltDemo = clt.CentralLimitTheoremDemo(sampleDistribution)
    n_vals = [2, 3, 10, 30]
    for N in n_vals:
        cltDemo.run_sample_demo(N = N, plot = True, num_bins = 40)
```

This produces the following output images.

![alt tag](https://github.com/mattnedrich/CentralLimitTheoremDemo/blob/master/sample_output/uniform_dist.png)

![alt tag](https://github.com/mattnedrich/CentralLimitTheoremDemo/blob/master/sample_output/uniform_n_2.png)

![alt tag](https://github.com/mattnedrich/CentralLimitTheoremDemo/blob/master/sample_output/uniform_n_3.png)

![alt tag](https://github.com/mattnedrich/CentralLimitTheoremDemo/blob/master/sample_output/uniform_n_10.png)

![alt tag](https://github.com/mattnedrich/CentralLimitTheoremDemo/blob/master/sample_output/uniform_n_30.png)
