# InferencePipeline for dataset using Huggingface
Pipeline() is userful to inferencing on different task by using specific model from Huggingface Hub. The following rules are applicable for any kind of model.
Here i use the pipeline for text-classification task.
# As a pipeline is mainly made of model and tokenizer -
1. The model link for text classification from hub. (https://huggingface.co/amandakonet/climatebert-fact-checking).
   The model take input 'claim' and 'evidence' as pairs. Thats why i frind out the list of claim and evidence from dataset and pass to the model as pairing through 
   pipeline.
3. Tokenizer of respective model.
4. Dataset from huggingface (https://huggingface.co/datasets/amandakonet/climate_fever_adopted).This dataset have output/lebel in 3 category.
5. There are different parameter to build up a task specific pipeline. some are very important, like
    device - define the device (CPU,GPU) on which pipeline will be allocated. device_map="auto" to allow Accelerate to automatically determine how to load and store 
    the model weights.
    Batch size - Alltime batching is not important. for more details (https://huggingface.co/docs/transformers/main_classes/pipelines#pipeline-batching)
    task
    model
    tokenizer
6. To execute pipeline we have to pass data. data can be dataset or generator (webserver with Http request or database) 
