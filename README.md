# LLAMA INFERENCE

Running LLAMA 7B model with 4 bit quantization on google colab using [GPTQ](https://github.com/IST-DASLab/gptq).


## Dependencies
`torch`: tested on v1.13.1+cu116
`transformers`: tested on v4.27.0.dev0(required)
`datasets`: tested on v2.10.1
`safetensors`: tested on v0.3.0
(to run 4-bit kernels: setup for compiling PyTorch CUDA extensions, see also <https://pytorch.org/tutorials/advanced/cpp_extension.html>, tested on CUDA 11.6)

## Memory Usage
|                           Model                                                             | Bits | memory(MiB) | benchmark(ppl) | Wikitext2 |   PTB     |    C4   | checkpoint size(GB) |
| ------------------------------------------------------------------------------------------- | ---- | ----------- | ------------- | --------- | --------- | ------- | ------------------- |
| [LLaMa-7B](https://arxiv.org/abs/2302.13971) with [GPTQ](https://arxiv.org/abs/2210.17323)  |  8   |    7748     |    5.39   |    5.67   |   8.81   |   7.08  |          6.5        |
| [LLaMa-7B](https://arxiv.org/abs/2302.13971) with [GPTQ](https://arxiv.org/abs/2210.17323)  |  4   |    4740     |    6.23   |    6.79   |   10.67   |   8.28  |          3.5        |
| [LLaMa-7B](https://arxiv.org/abs/2302.13971) with [GPTQ](https://arxiv.org/abs/2210.17323)  |  3   |    3852     |    11.43  |    17.94  |   31.44   |   19.65  |          2.75        |
| [LLaMa-7B](https://arxiv.org/abs/2302.13971) with [GPTQ](https://arxiv.org/abs/2210.17323)  |  2   |    3076     |    4152  |    30749  |   45936   |   5045  |          2.0        |
| [LLaMa-13B](https://arxiv.org/abs/2302.13971) with [GPTQ](https://arxiv.org/abs/2210.17323) |  2   |    5275     |    6903   |   13203   |   1384   |  8.34  |          5.06        |