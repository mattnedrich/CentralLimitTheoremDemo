## Central Limit Theorem Demo

## Usage

import central_limit_theorem_demo as clt
```python
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
