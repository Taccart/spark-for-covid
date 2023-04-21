# Spark for COVID public data 
Some examples for Spark notebooks for COVID public data using JupyterLab

## Starting your Jupyter instance
Start a local Jupyter server using /home/$USER/Documents/jupyter-work/ as your local folder for notebooks:
```
  mkdir /home/$USER/Documents/jupyter-work/ 
  
  docker run  \
	  -p 8888:8888                                              \
	  --memory 10gb                                             \
	  --memory-swap 8gb                                         \
	  --network bridge --rm                                     \
	  -e JUPYTER_ENABLE_LAB=yes                                 \
	  -e JUPYTER_TOKEN=token                                    \
	  -v /home/$USER/:/home/$USER/                              \
	  -v /home/$USER/Documents/jupyter-work/:/home/jovyan/work/ \
	  jupyter/all-spark-notebook:2021-01-01
```
Once started, your own jupyter instance should be running : open
`[http://127.0.0.1:8888](http://127.0.0.1:8888)`, the token to use is "`token`".

## Content

### Spark for EUDRAVigilance : 
European database of *suspected* adverse drug reaction reports.
- Data source :  Human datasets in EudraVigilance 
- location: [https://www.adrreports.eu/](https://www.adrreports.eu/)

> EudraVigilance is the system for managing and analysing information on *SUSPECTED* adverse reactions to medicines which have been authorised or being studied in clinical trials in the European Economic Area (EEA). 
> The European Medicines Agency (EMA) operates the system on behalf of the European Union (EU) medicines regulatory network.

Example of datasets:
* [COVID-19 MRNA VACCINE MODERNA CX-024414](https://dap.ema.europa.eu/analyticsSOAP/saw.dll?PortalPages&amp;PortalPath=%2Fshared%2FPHV%20DAP%2F_portal%2FDAP&amp;Action=Navigate&amp;P0=1&amp;P1=eq&amp;P2=%22Line%20Listing%20Objects%22.%22Substance%20High%20Level%20Code%22&amp;P3=1+40983312)
* [COVID-19 MRNA VACCINE PFIZER-BIONTECH TOZINAMERAN](https://dap.ema.europa.eu/analyticsSOAP/saw.dll?PortalPages&amp;PortalPath=%2Fshared%2FPHV%20DAP%2F_portal%2FDAP&amp;Action=Navigate&amp;P0=1&amp;P1=eq&amp;P2=%22Line%20Listing%20Objects%22.%22Substance%20High%20Level%20Code%22&amp;P3=1+42325700)
* [COVID-19 VACCINE ASTRAZENECA (CHADOX1 NCOV-19)](https://dap.ema.europa.eu/analyticsSOAP/saw.dll?PortalPages&amp;PortalPath=%2Fshared%2FPHV%20DAP%2F_portal%2FDAP&amp;Action=Navigate&amp;P0=1&amp;P1=eq&amp;P2=%22Line%20Listing%20Objects%22.%22Substance%20High%20Level%20Code%22&amp;P3=1+40995439)
* [COVID-19 VACCINE JANSSEN AD26.COV2.S](https://dap.ema.europa.eu/analyticsSOAP/saw.dll?PortalPages&amp;PortalPath=%2Fshared%2FPHV%20DAP%2F_portal%2FDAP&amp;Action=Navigate&amp;P0=1&amp;P1=eq&amp;P2=%22Line%20Listing%20Objects%22.%22Substance%20High%20Level%20Code%22&amp;P3=1+42287887)
* and more ...

Notebook : [EUDRA Vexperiencesigilance.ipynb](./EUDRA Vigilance.ipynb)

### Spark for VAERS
- Data source : Vaccine Adverse Event Reporting System, U.S. Department of Health & Human Services
- location : [https://vaers.hhs.gov](https://vaers.hhs.gov)
> VAERS is a *passive reporting* system, meaning it *relies on individuals* to send in reports of their experiences to CDC and FDA. 
> VAERS *is not designed to determine if a vaccine caused a health problem*, but is especially useful for detecting unusual or unexpected patterns of adverse event reporting that might indicate a possible safety problem with a vaccine. 
> This way, VAERS can provide CDC and FDA with valuable information that additional work and evaluation is necessary to further assess a possible safety concern.

Datasets: 
* [https://vaers.hhs.gov/data/datasets.html]([https://vaers.hhs.gov/data/datasets.html])

Notebook : [VAERS HSS.ipynb](./VAERS%20HHS.ipynb)
