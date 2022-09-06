# Audio Scene Recognition

## What’s the point?

The service receives an audio file and uses it as an input for a trained model.

##  Model details:

The service receives an WAV audio file and uses it as an input to the convolution model, based on a convolution neural network trained in half-precision using a mixture of natural and synthetic data, and outputs the result of the speech sample recognition in form of a text. The model runs on a GPU equipped with tensor cores to provide greater service bandwidth. The input audio file size is limited to 4Mb, in practice the optimal duration of the processed audio track should be no more than 90 seconds for 320 kbps audio.

## How does it work?

The user must provide the following inputs in order to start the service and get a response:

Inputs:

 -   `endpoint`: ?
 -   `method`: audio2scene.
 -   `input_path`: Path to '\*.txt' file containing JSON representation of input argument 'file@data' and its value - path to '\*.wav' input audio file.

Example of input file content:

```
{"file@data": "samples/sample.wav"}
```


## What to expect from this service?

Input audio:
samples/sample.wav

Response: 
`text : top 5 labels in every 3 seconds in input audio`
