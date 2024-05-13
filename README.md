# mT5ForTranslate_English2Chinese

在[google/mt5-small](https://huggingface.co/google/mt5-small)模型基础上，使用Tiny Stories数据集进行fine-tune  
翻译方向为English to Chinese  
评估指标为BLEU，也可选择其他评估指标  
模型公开在[Jchew/mT5ForTranslate_English2Chinese](https://huggingface.co/Jchew/mT5ForTranslate_English2Chinese)  
使用方法：
```Python
    from transformers import AutoModelForSeq2SeqLM
    from transformers import AutoTokenizer
    tokenizer = AutoTokenizer.from_pretrained("Jchew/mT5ForTranslate_English2Chinese")
    model = AutoModelForSeq2SeqLM.from_pretrained("Jchew/mT5ForTranslate_English2Chinese")
    prefix:"Translate English into Chinese:"
    english_text = "hello,I'm Bob"
    inputs = tokenizer(prefix + english_text,padding = True,truncation=True)
    outputs = model.generate(**inputs)
    print(tokenizer.decode(outputs))
```
    
    
