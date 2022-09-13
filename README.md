first install scoop (from https://scoop.sh/)

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser # Optional: Needed to run a remote script the first time
irm get.scoop.sh | iex
```

install miniconda with scoop

```powershell
scoop bucket add extras
scoop install miniconda3
```

setup conda

```powershell
conda init powershell
conda config --add channels conda-forge
conda config --set channel_priority strict
conda config --set auto_activate_base false
conda config --set env_prompt '({name})'
```

restart powershell and run below in this folder

```powershell
conda create -p .env --file conda-requirements.txt
conda activate .\.env\
pip install -r .\requirements.txt
```

restart vs code