1. srun --pty -p titanx-short --gres=gpu:1 --mem 20000 -t 0-03:00 /bin/bash

2. python -c 'import torch; print(torch.cuda.is_available())'

3. sacct -j JOBID -o jobid,submit,start,end,state

4. squeue -u USERNAME

5. unzip test.zip -d test

6. gdrive_download GDRIVE_ID FILE_NAME

7. nvcc --version

8. ln -s ../FaceDetection-DSFD/weights/ .

9. unlink weights/weights
