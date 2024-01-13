# In Bound Bank Bot 0.1

## Technologies:
1. ASR: Whisper
2. TTS: Conqui YourTTS
3. NLU: RASA

## Dependencies:
1. Please clone following reposiotries: 
```
git clone https://github.com/Idrak-Pak/idrak_utils.git #Idrak Utils
git clone https://github.com/m-aliabbas/bank_bot bank_nlu #Bank NLU
git clone https://github.com/Idrak-Pak/TTS.git #TTS
git clone https://github.com/Idrak-Pak/whisper.git #Whisper

```
## Installation Steps (Ubantu and Mac):
1. conda create --name in_bound_bot_env python=3.10
2. conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
3. conda activate in_bound_bot_env
4. pip install -r requirements.txt

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
rasa run -m models/nlu-20240113-101342-unproductive-string.tar.gz --enable-api

2. Run following commands to start BOT: 
cd bank_bot
conda activate in_bound_bot_env
```python control.py or python main.py```

## Installation Steps (for Windows):
1. conda create --name in_bound_bot_env python=3.10

2. conda activate in_bound_bot_env

3. sudo apt install nvidia-cuda-toolkit
3. conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia

4. Install other dependencies:
cd bank_bot
pip install -r window_requirements.txt

5. Download and Install espeak-ng:
https://github.com/espeak-ng/espeak-ng/releases

Note: Download and install the latest 64-bit version of eSpeak NG (no version constraints).

6. Set the espeak path as per your system if you get espeak-ng not found error (It can be checked by running "espeak-ng --version"). Search for espeak folder (Normally at C:\Program Files (x86)\eSpeak NG) and add it's path to a file and put it in anaconda.d (You will find this in anaconda3 folder) folder. For Example, You can 
create a "add_espeak.bat" file with the following contents for putting in anaconda.d: 
set "PATH=C:\Program Files (x86)\eSpeak NG;%PATH%"



## RASA Specific Installation Steps (for Windows):
1. conda create --name rasa_env python=3.10
2. conda activate rasa_env
3. pip3 install rasa[spacy]
4. python -m spacy download en_core_web_lg

References (for installation TTS on windows):
0. https://tts.readthedocs.io/en/latest/installation.html
1. https://stackoverflow.com/questions/66726331/how-can-i-run-mozilla-tts-coqui-tts-training-with-cuda-on-a-windows-system
2. https://stackoverflow.com/questions/75204635/how-can-i-run-mozilla-tts-coqui-tts-training-with-cuda-on-a-windows-system?noredirect=1&lq=1


#### common problem with ubantu LTS 22:
Could not load library libcudnn_ops_infer.so.8. Error: libcudnn_ops_infer.so.8: cannot open shared object file: No such file or directory
Please make sure libcudnn_ops_infer.so.8 is in your library path!

One Solution:
Find:
sudo find / -type f -name libcudnn_ops_infer.so.8

Add to path like:
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/mmb/anaconda3/envs/in_bound_env/lib/python3.10/site-packages/torch/lib

Note: It is also possible that this problem is not due to path. 

#### Dated: October, 2023
#### Developed at IDRAK AI
#### Developed by Muhammad Ali Abbas & Muhammad Musawar Baig
