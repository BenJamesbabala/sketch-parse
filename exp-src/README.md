This folder contains code to replicate results corresponding to `B, BC, BCP` in Table 1 and `B-R5, BC-R5, BCP-R5` in Table 3 in the paper. 

### Instructions for use

* Use `train_r5.py` to train model for results `B-R5, BC-R5, BCP-R5` in Table 3.

For `BCP-R5`, run
```
python train_r5.py --segnetLoss --lambda1 1.0 --GTpath <train gt images path here> --IMpath <train images path here> 
```

For `BC-R5`, run
```
python train_r5.py --segnetLoss --lambda1 0.0 --GTpath <train gt path here> --IMpath <train images path here> 
```

For `B-R5`, run
```
python train_r5.py --lambda1 0.0 --GTpath <train gt images path here> --IMpath <train images path here> 
```

To get a description for each flag used, run
```
python train_r5.py -h
```



* Use `train_r1.py`  to train model for results `B, BC, BCP` in Table 1.

For `BCP`, run
```
python train_r1.py --segnetLoss --lambda1 1.0 --GTpath <train gt images path here> --IMpath <train images path here> 
```

To get a description for each flag used, run
```
python train_r1.py -h
```


* Run `table1.py`, `table3.py` to evaluate the downloaded  `.pth` files and get results corresponding to table 1 and table 3 in the paper.

Place the downloaded files in the folder `data/snapshots` and place the downloaded annotated sketches in then run `table1.py` and `table3.py`.
The .pth files can be downloaded from [here](http://val.serc.iisc.ernet.in/star_snapshots/).

`pred_gt.txt` contains the predicted label and the real label of each sketch image. The predicted label can also be found real time using a trained classifier. The architecture of the classifier is mentioned in the supplementary material and the training policy / data is mentioned in the paper. This file is used during evaluation.
