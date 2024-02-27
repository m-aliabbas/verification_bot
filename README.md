# Validation Version 0.3

## RASA Specific Installation Steps (for Ubantu):
1. conda create --name rasa_env python=3.10
2. conda activate rasa_env
3. pip3 install rasa[spacy]==3.6.5
4. python -m spacy download en_core_web_lg

## RASA Specific Installation Steps (for Mac):
1. conda create --name rasa_env python=3.10
2. conda activate rasa_env
3. pip3 install rasa[metal]
4. python -m spacy download en_core_web_lg

## Path Settings:
Please add the path of repos cloned above to `path_config.py` and also set the RASA_URL, INPUT_DEVICE and OUTPUT_DEVICE in `general_config.py`.

## Normal Usage:
1. Start RASA NLU in it's virtual environment:
cd rasa_nlu
conda activate nlu_env

Latest Model train on latest data:

rasa run -m models/20240227-103645-constant-ostrich_version_04.tar.gz --enable-api


## RASA Specific Installation Steps (for Windows):
1. conda create --name rasa_env python=3.10
2. conda activate rasa_env
3. pip3 install rasa[spacy]
4. python -m spacy download en_core_web_lg


#### Dated: Feb 20th, 2024
#### Developed at IDRAK AI
#### Developed by Muhammad Ali Abbas & Muhammad Musawar Baig
