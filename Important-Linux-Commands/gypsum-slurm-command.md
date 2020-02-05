1. srun --pty -p titanx-short --gres=gpu:1 --mem 20000 -t 0-03:00 /bin/bash

2. python -c 'import torch; print(torch.cuda.is_available())'

3. sacct -j JOBID -o jobid,submit,start,end,state

4. squeue -u USERNAME

5. unzip test.zip -d test

6. gdrive_download GDRIVE_ID FILE_NAME

7. nvcc --version

8. ln -s ../FaceDetection-DSFD/weights/ .

9. unlink weights/weights




Download Data From Kaggle:

1. Copy Kaggle download link (this one: https://www.kaggle.com/c/16880/datadownload/dfdc_train_all.zip)
2. Open a new browser tab
3. Activate Network Inspector (in Firefox it is Ctrl + Shift + E)
4. Paste the download link in browser url and hit enter
5. Cancel download
6. In the network inspector, you will see the request that the browser made to download the file
7. Right click, Copy > Copy as cURL (POSIX)
8. Paste the copied command in a remote VM, AND add the option to output to a file: -o dfdc_train_all.zip

8.1. (Optional) Add --progress-bar flag to view download progress.
