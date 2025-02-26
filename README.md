# FER_POSTER_ADA (add alignment function to FER with backbone POSTER)
This project is for the Advanced Machine Learning class at SeoulTech [1st semester - 2023] Instead of using an MLP head for the classifier, I added the "AdaFace: Quality Adaptive Margin" classifier head on top of the POSTER backbone. My detailed modification is in the "models" folder. My detail results are shown in the "Advanced_Machine_Learning_Project.pdf" file in this source code

### Preparation
- create conda environment (we provide requirements.txt)

- Data Preparation

  Download [RAF-DB] dataset, and make sure it have a structure like following:
 
	```
	- data/raf-basic/
		 EmoLabel/
		     list_patition_label.txt
		 Image/aligned/
		     train_00001_aligned.jpg
		     test_0001_aligned.jpg
		     ...
	```

- Pretrained model weights
 - Put entire `pretrain` folder under `models` folder.

	```
	- models/pretrain/
		 ir50.pth
		 mobilefacenet_model_best.pth.tar
		     ...
	```

### Testing

- put best model under `checkpoint ` folder. You can evaluate our model on RAD-DB dataset by running: 

```
python test.py --checkpoint checkpoint/rafdb_best.pth -p
```

### Training
Train on RAF-DB dataset:
```
python train.py --gpu 0,1 --batch_size 200
```
You may adjust batch_size based on your # of GPUs. Usually bigger batch size can get higher performance. We provide the log in  `log` folder. You may run several times to get the best results. 






## Acknowledgments

Our implementation and experiments based on the official of ADA [AdaFace: Quality Adaptive Margin for Face Recognition] code and POSTER [ POSTER: A Pyramid Cross-Fusion Transformer Network for Facial Expression Recognition.] code.  

```
@misc{kim2023adaface,
      title={AdaFace: Quality Adaptive Margin for Face Recognition}, 
      author={Minchul Kim and Anil K. Jain and Xiaoming Liu},
      year={2023},
      eprint={2204.00964},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```


code: https://github.com/zczcwh/POSTER

```
@article{zheng2022poster,
  title={Poster: A pyramid cross-fusion transformer network for facial expression recognition},
  author={Zheng, Ce and Mendieta, Matias and Chen, Chen},
  journal={arXiv preprint arXiv:2204.04083},
  year={2022}
}
```
code: 



