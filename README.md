# TensorFlow Lite Deep Compressor

## Build the snap

This snap is not available via the Snap Store.
You will need to build it from source yourself.
Clone this repository and then run the following command in the cloned directory:

```
snapcraft -v
```

We recommend building on Ubuntu Desktop 24.04 or Ubuntu Server 24.04.

## Install the snap

```
snap install --dangerous ./deep-compressor_*.snap
```

## How to use

```
$ deep-compressor -i ~/Downloads/Parrot.red.macaw.1.arp.750pix.jpg
INFO: Created TensorFlow Lite XNNPACK delegate for CPU.
time: 28.257ms
```

## Advanced usage

This app provides command line arguments to override its default behaviour.

```
$ deep-compressor --help
usage: deep_compression_script.py [-h] [-i IMAGE] [-m MODEL_FILE]
                           [--input_mean INPUT_MEAN] [--input_std INPUT_STD]
                           [--num_threads NUM_THREADS] [-e EXT_DELEGATE]
                           [-o EXT_DELEGATE_OPTIONS]

optional arguments:
  -h, --help            show this help message and exit
  -i IMAGE, --image IMAGE
                        image to be classified
  -m MODEL_FILE, --model_file MODEL_FILE
                        .tflite model to be executed
  --input_mean INPUT_MEAN
                        input_mean
  --input_std INPUT_STD
                        input standard deviation
  --num_threads NUM_THREADS
                        number of threads
  -e EXT_DELEGATE, --ext_delegate EXT_DELEGATE
                        external_delegate_library path
  -o EXT_DELEGATE_OPTIONS, --ext_delegate_options EXT_DELEGATE_OPTIONS
                        external delegate options, format: "option1: value1;
                        option2: value2"
```

## Debugging

Python 3.8 and the bundled dependencies are exposed by the snap under the `deep-compressor.python` app.
This can be used to run custom Python scripts, or get an interactive Python shell.

```
$ deep-compressor.python
Python 3.8.19 (default, Apr 27 2024, 21:20:48)
[GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import tflite_runtime
>>> tflite_runtime.__version__
'2.14.0'
>>>
```
