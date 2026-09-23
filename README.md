# Predict-the-next-word-with-lstm

A simple Streamlit web app that predicts the next word in a sentence using a trained LSTM (Long Short-Term Memory) neural network, built with TensorFlow/Keras.

How it works
Type in a sequence of words (e.g. To be or not to)
The app tokenizes your text using a pre-trained tokenizer
A trained LSTM model predicts the most likely next word
The predicted word is displayed on screen
Project structure
LSTM RNN/
├── app.py                 # Streamlit app (entry point)
├── next_word_lstm.h5      # Trained LSTM model
├── tokenizer.pickle        # Fitted tokenizer used during training
├── hamlet.txt              # Training text corpus (Shakespeare's Hamlet)
├── EXPERIMENT.IPYNB        # Notebook used to train the model
└── README.md
Requirements
Python 3.10 (recommended — newer versions may have TensorFlow compatibility issues)
TensorFlow 2.15.x (Apple Silicon: tensorflow-macos + tensorflow-metal)
Streamlit
NumPy

See requirements.txt for exact versions.

Setup
Create and activate a virtual environment (recommended: Python 3.10)
bash
   conda create -n stable_environment python=3.10 -y
   conda activate stable_environment
Install dependencies
bash
   pip install -r requirements.txt

Apple Silicon (M1/M2/M3) users: use tensorflow-macos and tensorflow-metal instead of plain tensorflow — the generic PyPI build is not reliably compiled for arm64 and can cause the app to crash on load.

Run the app
bash
   streamlit run app.py
Open the local URL Streamlit prints (usually http://localhost:8501) in your browser.
Usage
Enter a partial sentence in the text box (e.g. To be or not to)
Click "predict next word"
The app will display its prediction for the next word in the sequence
Notes
The model was trained on Shakespeare's Hamlet, so predictions reflect that vocabulary and style — it won't perform well on unrelated modern text.
If you see a ValueError about unrecognized keyword arguments (e.g. time_major) when loading the model, your TensorFlow/Keras version is too new for this model file. Install TensorFlow 2.15.x specifically, which uses the compatible legacy Keras 2 format.
If the app crashes with a segmentation fault on Apple Silicon, it usually means the wrong (non-native) TensorFlow build is installed — switch to tensorflow-macos + tensorflow-metal.
