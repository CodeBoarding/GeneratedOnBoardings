```mermaid
graph LR
    Visualization_Plotting["Visualization & Plotting"]
    qqplot["qqplot"]
    plot_shift["plot_shift"]
    plot_paired["plot_paired"]
    plot_circmean["plot_circmean"]
    plot_rm_corr["plot_rm_corr"]
    plot_blandaltman["plot_blandaltman"]
    Visualization_Plotting -- "exposes" --> qqplot
    Visualization_Plotting -- "exposes" --> plot_shift
    Visualization_Plotting -- "exposes" --> plot_paired
    Visualization_Plotting -- "exposes" --> plot_circmean
    Visualization_Plotting -- "exposes" --> plot_rm_corr
    Visualization_Plotting -- "exposes" --> plot_blandaltman
    qqplot -- "utilizes" --> _ppoints
    plot_shift -- "utilizes" --> adjacent_values
    plot_paired -- "utilizes" --> seaborn
    plot_circmean -- "utilizes" --> matplotlib
    plot_rm_corr -- "utilizes" --> statsmodels
    plot_rm_corr -- "utilizes" --> seaborn
    plot_blandaltman -- "utilizes" --> matplotlib
    plot_blandaltman -- "utilizes" --> scipy_stats
    click Visualization_Plotting href "https://github.com/CodeBoarding/GeneratedOnBoardings/blob/main/pingouin/Visualization_Plotting.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/GeneratedOnBoardings)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/demo)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The `pingouin.plotting` subsystem serves as the primary visualization interface within the Pingouin library, offering a suite of specialized statistical plots. It acts as a facade, exposing various plotting functions that encapsulate the logic for generating specific types of visualizations. Each plotting function (`qqplot`, `plot_shift`, `plot_paired`, `plot_circmean`, `plot_rm_corr`, `plot_blandaltman`) is a self-contained component responsible for its specific plot type, handling data preparation, statistical calculations, and rendering using underlying libraries like Matplotlib and Seaborn. The `Visualization & Plotting` component orchestrates access to these individual plotting functionalities, providing a unified entry point for users.

### Visualization & Plotting [[Expand]](./Visualization_Plotting.md)
The overarching component providing a comprehensive set of utilities for generating various statistical plots within the `pingouin` library. It serves as the entry point for users to access visualization functionalities.


**Related Classes/Methods**:

- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L219-L407" target="_blank" rel="noopener noreferrer">`pingouin.plotting.qqplot`:219-407</a>
- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L665-L898" target="_blank" rel="noopener noreferrer">`pingouin.plotting.plot_shift`:665-898</a>
- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L410-L662" target="_blank" rel="noopener noreferrer">`pingouin.plotting.plot_paired`:410-662</a>
- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L1033-L1160" target="_blank" rel="noopener noreferrer">`pingouin.plotting.plot_circmean`:1033-1160</a>
- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L901-L1030" target="_blank" rel="noopener noreferrer">`pingouin.plotting.plot_rm_corr`:901-1030</a>
- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L29-L193" target="_blank" rel="noopener noreferrer">`pingouin.plotting.plot_blandaltman`:29-193</a>


### qqplot
Generates Quantile-Quantile (Q-Q) plots to assess if a dataset's distribution matches a theoretical distribution, a fundamental tool for normality testing and distribution comparison. It relies on `scipy.stats.probplot` for core calculations and `matplotlib.pyplot` for rendering.


**Related Classes/Methods**:

- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L196-L216" target="_blank" rel="noopener noreferrer">`pingouin.plotting._ppoints`:196-216</a>


### plot_shift
Creates plots to visualize shifts or changes in data distributions, useful for comparing groups or pre-post measurements, often employed in effect size visualization. It utilizes `seaborn.pointplot` and `seaborn.boxplot` for visualization.


**Related Classes/Methods**:

- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L809-L815" target="_blank" rel="noopener noreferrer">`pingouin.plotting.adjacent_values`:809-815</a>


### plot_paired
Visualizes paired observations, typically displaying individual data points and connecting them to show trends or differences, crucial for repeated measures designs. It leverages `seaborn.lineplot` and `seaborn.scatterplot` for individual data points and lines, and `seaborn.boxplot` for summary statistics.


**Related Classes/Methods**:

- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L410-L662" target="_blank" rel="noopener noreferrer">`pingouin.plotting.plot_paired`:410-662</a>


### plot_circmean
Plots circular data, specifically the circular mean and potentially its confidence intervals or measures of dispersion, catering to specialized statistical domains. It uses `matplotlib.patches.Circle` and `matplotlib.axes.Axes.arrow` for drawing the circular plot and mean vector.


**Related Classes/Methods**:

- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L1033-L1160" target="_blank" rel="noopener noreferrer">`pingouin.plotting.plot_circmean`:1033-1160</a>


### plot_rm_corr
Generates plots to visualize repeated measures correlations, often showing individual subject trends alongside the overall correlation, vital for longitudinal studies. It integrates with `statsmodels.formula.api.ols` for statistical modeling and `seaborn.FacetGrid`, `seaborn.regplot`, and `seaborn.scatterplot` for visualization.


**Related Classes/Methods**:

- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L901-L1030" target="_blank" rel="noopener noreferrer">`pingouin.plotting.plot_rm_corr`:901-1030</a>


### plot_blandaltman
Generates Bland-Altman plots to assess the agreement between two different measurements or methods. It calculates mean differences and limits of agreement, and visualizes them with scatter plots and horizontal lines.


**Related Classes/Methods**:

- <a href="https://github.com/raphaelvallat/pingouin/blob/main/src/pingouin/plotting.py#L29-L193" target="_blank" rel="noopener noreferrer">`pingouin.plotting.plot_blandaltman`:29-193</a>




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)