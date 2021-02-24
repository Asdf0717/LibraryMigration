# A Large-Scale Empirical Study on Java Library Migrations: Trends and Rationales

## Data Availibility

The dataset of migration commits is available [here](data/migrations.xlsx).
The more compact dataset of migration rules is [here](data/rules.xlsx).
We use [get_prs_by_commits.py](get_prs_by_commits.py) Python script to get issues and PRs [here](data/prs.xlsx).
We then use [get_coding_data.py](get_coding_data.py) to aggregate coding data [here](data/coding_commits_prs.xlsx).
The final coding is done entirely manually in [this file](data/coding.xlsx).
Other large datasets will be archived in Zenodo upon acceptance.

## Results

Results for RQ1 can be found in [plot_depchgs.ipynb](plot_depchgs.ipynb).
Results for RQ2 can be found in [plot_migrations.ipynb](plot_migrations.ipynb).
The initial coding book can be found in [CODING.md](CODING.md) and the results can be found in [coding.ipynb](coding.ipynb)

## Development

We use Anaconda for development. 
Please configure to use a new Conda environment with Python 3.8 and [requirements](requirements.txt) satisfied.

```shell script
conda create -n LibraryMigration python=3.8
conda activate LibraryMigration
conda install -c r r-irkernel r-essentials r-corrplot r-pscl
conda install nodejs -c conda-forge --repodata-fn=repodata.json
conda install -c conda-forge ipysankeywidget
conda install -c plotly plotly-orca
python -m pip install -r requirements.txt
jupyter labextension install jupyterlab-plotly@4.14.3
jupyter labextension install @jupyter-widgets/jupyterlab-manager plotlywidget@4.14.3
```

Format all Python file like this

```shell script
autopep8 --in-place --aggressive --max-line-length 119 *.py 
```
