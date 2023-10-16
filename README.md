# GenderRecognition-MLProject
Gender Recognition Using Real Time Voice Input or by using .wav file input.Built using a deep learning model from TensorFlow.Read this [docs](https://www.thepythoncode.com/article/gender-recognition-by-voice-using-tensorflow-in-python) for more information.

## Requirements
- TensorFlow 2.x.x
- Scikit-learn
- Numpy
- Pandas
- PyAudio
- Librosa

### Installing the required libraries:
  pip3 install -r requirements.txt

## Dataset used
Extract the data file before using it for data preparation.
[Mozilla's Common Voice](https://www.kaggle.com/mozillaorg/common-voice)

Used [Mel Spectrogram](https://librosa.org/doc/main/generated/librosa.feature.melspectrogram.html) feature extraction technique to get a vector of a fixed length from each voice sample, the [data](data.rar) folder contain only the features and not the actual mp3 samples (the dataset is too large, about 13GB).

If you wish to download the dataset and extract the features files (.npy files) on your own, [`preparation.py`](preparation.py) is the responsible script for that, once you unzip it, put `preparation.py` in the root directory of the dataset and run it. 

This will take sometime to extract features from the audio files and generate new .csv files.

## Required Packages
You can manually download all the required package mention in [`requirements.txt`](requirements.txt) or use pip python package installer to install it from the file:

    pip install -r requirements.txt


## Training
You can customize your model in [`utils.py`](utils.py) file under the create_model() function and then run:

    python/python3 train.py

## Testing
[`test.py`](test.py) is the code responsible for testing your audio files or your voice:

    python/python3 test.py


- For instance, to get gender of the file `test-samples/27-124992-0002.wav`, you can:

      python3 test.py --file "test-samples/27-124992-0002.wav"

    **Output:**

      Result: male
      Probabilities:     Male: 96.36%    Female: 3.64%

- For instance, to get gender of the file `test-samples/22-121148-0001.wav`, you can:

      python3 test.py --file "test-samples/22-121148-0001.wav"

    **Output:**

      Result: female
      Probabilities:     Male: 3.18%    Female: 96.82%

There are some audio samples in [test-samples](test-samples) folder for you to test with, it is grabbed from [LibriSpeech dataset](http://www.openslr.org/12).

To perform real-time gender voice recognition:

      python/python3 test.py

Wait until you see `"Start Recording....."` prompt and start talking, it will stop recording as long as you stop talking.

## Live Demonstration Video
  - Video Link:
    [Click](https://youtu.be/Hq-xQPMarMc)
