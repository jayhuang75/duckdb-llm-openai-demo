# Background and Context

This demo is for one of weekend build and learn which publish in Medium:
To analysis the Canada Government's [Open data Inventory](https://open.canada.ca/en/search/inventory)

## Local LLAMA2 stup

```bash

git clone https://github.com/ggerganov/llama.cpp.git
cd llama.cpp

## linux
make

## mac
LLAMA_METAL=1 make

## download
wget https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGML/resolve/main/llama-2-7b-chat.ggmlv3.q4_K_S.bin


## base on the https://huggingface.co/TheBloke/Llama-2-13B-chat-GGML/discussions/14
## note: 
##  latest llama.cpp is no longer compatible with GGML models. The new model format, GGUF, was merged ##  recently. As far as llama.cpp is concerned, GGML is now dead.
## we need to convert the model to the gguf
./convert-llama-ggml-to-gguf.py --eps 1e-5 -i ./models/llama-2-7b-chat.ggmlv3.q4_K_S.bin -o ./models/llama-2-7b-chat.ggmlv3.q4_K_S.gguf.bin


## test the model
./main -m models/llama-2-7b-chat.ggmlv3.q4_K_S.gguf.bin --temp 0 -p "What is the capital of France?"


```
