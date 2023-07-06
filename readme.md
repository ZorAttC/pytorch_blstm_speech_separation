# Pytorch_BLSTM_Speech_Separation

This is a BLSTM vocal separation network based on pytorch (this model only implements double vocal mixture extraction).

## Basic process

### Prepare data

To prepare data, you can use the scripts in the preprocess folder to prepare training data and verification data. By default, audio with a sampling rate of 8k is used. If you use 16k audio, please perform downsampling in downsample.py. mix_2speaker.py will mix two audios, align the length to the longest audio, and output the wav file to the specified folder

## Feature Extraction

Use extract_feats.py for feature extraction, this step will use the STFT algorithm to transform the audio file to extract features. The extracted features will be used for model training.

## Model training

The basic structure of the model: MLP encoder -> BLSTM ->MLP decoder

The output is obtained by multiplying the decoded image mask with the input.

Running the train.py file will train the model and save it

## Audio decoding

Run the decode.py file, the decoded audio will be saved in output

## Precautions

Before running, please search for 'D:\' to find the corresponding path string, and modify it to the path where your project file is located

## References

https://github.com/https://github.com/aishoot/LSTM_PIT_Speech_Separation.gitaishoot/LSTM_PIT_Speech_Separation.git

https://github.com/xuchenglin28/speech_separation.git (based on this project implementation)

Speech dataset from aishell
