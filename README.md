# llama-lora-chinese-couplet
A simple llama-lora end to end example to show its potential to train a Chinese Couplet AI
- int8 LLaMa + LoRA = Finetune in a consumer GPU <= 16G vram!

## Slides (TBD), topics included but not limited to
- LLM, Pretrain, Finetune
- [Quantization intro](https://huggingface.co/blog/hf-bitsandbytes-integration), [LLM.int8](https://arxiv.org/abs/2208.07339)
- [LoRA](https://arxiv.org/abs/2106.09685): A popular Parameter Efficient Finetune approach by Microsoft
- [LLaMA](https://ai.facebook.com/blog/large-language-model-llama-meta-ai/): A gift from Facebook to the research community
- [Alpaca](https://crfm.stanford.edu/2023/03/13/alpaca.html): A $600 approach to “distill 80%” of ChatGPT by Stanford
- [Alpaca-LoRA](https://github.com/tloen/alpaca-lora): An even cheaper approach from a Stanford student？


## Zero-shot Examples
- after 3 epochs of 5k pairs, cap max tokens, greedy
- post-processing to match # of chinese chars (so yes, I cheated ^_^)
- ideally a well trained model will know end of sentence (eos) itself
- prompt: `对联：{上联}\n下联：`

|上联| Base LLaMA | LLaMa_LoRA_A100_9mins |
| ----------- | ----------- | ----------- |
|春风得意花铺路| 沉浸落泥\n上联 | 月光听声风吹梦 |
|美丽中国魅力北京| 美丽中国魅力北京 | 历史浓浅中华梦境 |
|鱼书千里梦| 鱼肉烧肉\n | 鸟声万里声 |
|日落晚霞临古寺| 晚霞临古寺\n上 | 月映晨雨满梦境 |

- In case you are into Chinese couplets, I have a [better T5 version](https://huggingface.co/hululuzhu/chinese-couplet-t5-mengzi-finetune)
