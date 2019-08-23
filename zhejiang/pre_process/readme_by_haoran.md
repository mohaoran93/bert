
# run docker on 12
wget https://storage.googleapis.com/bert_models/2018_11_03/chinese_L-12_H-768_A-12.zip
unzip chinese_L-12_H-768_A-12.zip
nvidia-docker run -it -v /data/haoran:/data/haoran 8e978d76921e /bin/bash

cd bert
python3 zhejiang/run.py -data_dir /data/haoran/aspect_based_sentiment/bert/zhejiang/pre_process/preprocess_result_data -output_dir output -init_checkpoint /data/haoran/aspect_based_sentiment/bert/chinese_L-12_H-768_A-12/bert_model.ckpt -bert_config_file /data/haoran/aspect_based_sentiment/bert/chinese_L-12_H-768_A-12/bert_config.json -vocab_file /data/haoran/aspect_based_sentiment/bert/chinese_L-12_H-768_A-12/vocab.txt -device_map 0