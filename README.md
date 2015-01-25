## Central Limit Theorem Demo

## Usage
import central_limit_theorem_demo as clt

def create_uniform_sample_distribution():
    return range(100)

def create_sample_distribution():
    dist = [
    2,3,4,5,4,5,4,3,6,5,4,7,8,12,17,14,2,2,2,2,         # 0 - 20
    25,25,23,45,34,32,33,44,33,29,29,29,29,31,31,       # 20 - 40
    42,42,44,41,41,41,45,55,55,55,41,41,41,41,41,       # 40 - 60
    65,65,64,63,62,61,60,60,65,65,79,78,75,73,72,       # 60 - 80
    80,80,81,87,83,90,89,84,84,85,81,83,85,93,95]       # 80 - 100
    return dist

def run():
    sampleDistribution = create_uniform_sample_distribution()
    # Plot the original population distribution
    clt.plot_distribution(sampleDistribution, "Population Distribution", 0, 100, 20)
    # Plot a sampling distribution for values of N = 2, 3, 10, and 30
    cltDemo = clt.CentralLimitTheoremDemo(sampleDistribution)
    n_vals = [2, 3, 10, 30]
    for N in n_vals:
        cltDemo.run_sample_demo(N = N, plot = True, num_bins = 40)