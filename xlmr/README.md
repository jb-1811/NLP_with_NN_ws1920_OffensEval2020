The 'requirements.txt' has the necessary dependencies to run the following scripts. Make sure to use the correct Transformer library version (2.4.1) if not installing directly from the requirements.txt file.

Example command for running offenseval training: <br>
python run_language_modeling.py --train_data_file='data/all_lang/pretraining_data/train.tsv' --output_dir='pretrained_with_test-0/' --block_size=150 --do_train --line_by_line --mlm --model_name_or_path='xlm-roberta-base'
--model_type='xlmroberta' <br><br>

Example command for running offenseval training using further pretrained model created from 'run_language_modeling.py': <br>
python run_offenseval.py --data_dir data/all_lang/for_training_final_model/ --model_type xlmroberta --model_name_or_path pretrained_with_test-0 --output_dir / --task task_a --max_seq_length 150 --do_train --warmup_steps 2000 <br><br>

Example command for running offenseval training using out-of-the-box XLM-R model: <br>
python run_offenseval.py --data_dir data/all_lang/for_training_final_model/ --model_type xlmroberta --model_name_or_path xlm-roberta-base --output_dir exps_dir/ --task task_a --max_seq_length 150 --do_train --warmup_steps 2000 <br><br>

Example command for evaluating trained model on English: <br>
python run_offenseval.py --data_dir data/english/ --model_type xlmroberta --model_name_or_path xlm-roberta-base --output_dir exps_dir/ --task task_a --max_seq_length 150 --do_eval --language english --warmup_steps 2000 <br><br>

For visualizing the attentions, we have provided the notebook we adapted from https://github.com/jessevig/bertviz. <br>

We used this with Google Colab by uploading the trained model to Google drive, mounting the drive, and then loading the model into the notebook. 


