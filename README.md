# Audio-Transcription-and-Summarization

This project provides a Python script that utilizes the Hugging Face transformers library to transcribe audio files and generate summaries of the transcriptions. It's particularly useful for processing audio content like podcasts, interviews, or lectures to quickly get a text version and a concise summary.

Features
  1. Audio Transcription: Uses the Whisper model from OpenAI to accurately transcribe audio files.
  2. Text Summarization: Employs a BART-CNN model fine-tuned on the SAMSum dataset to generate concise summaries of the transcribed text.
  3. Batch Processing: Can process multiple audio files uploaded to the environment.

Requirements
  Python 3.6+
  transformers
  datasets
  torchaudio
  librosa
  torch
You can install the required libraries using pip.

  1. **Install Libraries**: This cell installs the necessary Python libraries like transformers, datasets, torchaudio, and librosa. These are           essential for working with audio data and natural language processing tasks like transcription and summarization.

  2. **Upload Audio Files**: This cell uses a function provided by Google Colab to allow you to upload audio files from your computer directly          into the Colab environment for processing.

  3. **Import Libraries and Set Device**: This cell imports specific modules from the installed libraries and sets up the computing device to be        used. It checks if a CUDA-enabled GPU is available and uses it for faster processing; otherwise, it defaults to using the CPU.

  4. **Load Whisper Model and Processor**: This cell downloads and loads a pre-trained Whisper model and its associated processor from Hugging          Face. The Whisper model is specifically designed for speech-to-text transcription. The model is then moved to the selected device (GPU or        CPU).

  5. **Define Transcription Function**: This cell defines a function called transcribe_audio. This function takes the path to an audio file,            loads the audio, resamples it to the required frequency for the Whisper model, processes it, and then uses the Whisper model to generate         a text transcription of the audio.

  6. **Load Summarization Model and Tokenizer**: This cell downloads and loads a pre-trained BART-CNN model and its tokenizer from Hugging Face.        This model is specifically trained for text summarization. The model is also moved to the selected device.

  7. **Define Summarization Function**: This cell defines a function called summarize_text. This function takes a block of text as input,               prepares it for the summarization model using the tokenizer, and then uses the BART-CNN model to generate a concise summary of the text.

  8. **Transcribe and Summarize Uploaded Files**: This cell loops through each of the audio files you uploaded. For each file, it calls the             transcribe_audio function to get the text transcription and then calls the summarize_text function to get a summary of that                      transcription. It then prints both the transcription and the summary for each file. It also stores these in lists.
 
  9. **Combine Transcripts and Generate Final Summary**: After processing individual files, this cell combines all the separate transcriptions          into one large block of text. It then uses the summarize_text function to generate a single, overall summary of the entire combined text.        Finally, it prints this final summary.
