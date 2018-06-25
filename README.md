## Facial Recognition
Dataset Obtained from: https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data

`Algorithms used:` CNN, ANN, Logistic Regression
### Environment Used for CNN :
TensarFlow supports GPU's so for this assignmemnt, I used GPU instance on Amazon Web Services. This allowed us to minimize training time for CNN algorithm,Below is how we setup this up.

`Select Instance Type: `
```
Instance Type :
g3.4xlarge (47 ECUs, 16 vCPUs, 2.7 GHz, Intel Xeon E5-2686 v4, 122 GiB memory,)
```

`Features of GPU instance: `

- High frequency Intel Xeon E5-2686 v4 (Broadwell) processors
- NVIDIA Tesla M60 GPUs, each with 2048 parallel processing cores and 8 GiB of video memory
- Number of GPU's 1
 Read More(ref.) : https://aws.amazon.com/ec2/instance-types/

 `AMI selected:`
AMI: Deep Learning AMI (Amazon Linux) Version 8.0 - ami-15634f6c (Ireland region)

Features: Comes with latest binaries of deep learning frameworks pre-installed in separate virtual environments: MXNet, TensorFlow, Caffe, Caffe2, PyTorch, Keras, Chainer, Theano and CNTK. Fully-configured with NVidia CUDA, cuDNN and NCCL as well as Intel MKL-DNN

### How To's :

##### 1. Create anaconda server (To run CNN on GPU):
1. Launch `EC2` instance with Deep learning ami mentioned above
2. Attatch elastic ip address to the server
3. Login to the server
`ssh -i <key.pem> ec2-user@<public dns name>`
4. Download latest anaconda application
 ``` wget https://repo.continuum.io/archive/Anaconda2-4.1.1-Linux-x86_64.sh ```
5. Run `./Anaconda2-4.1.1-Linux-x86_64.sh` on instance
6. Once you install anaconda server, you need to create ssh tunnel to the instance so that you can access jupyter notebook on the your local machine.
7. Now, On ec2 instance run `jupyter notebook --no-browser --port=8152`
`Note : below step will work only on macbook `
8. And on your local machine use below command,
`ssh -i <key.pem> -L 8152:localhost:8152 ec2-user@<public dns name>`
9. You can now access jupyter notebook on your local machine on `localhost:8152`

Read More :
https://hackernoon.com/aws-ec2-part-3-installing-anaconda-on-ec2-linux-ubuntu-dbef0835818a
https://towardsdatascience.com/setting-up-and-using-jupyter-notebooks-on-aws-61a9648db6c5

Other two algorithms can run on local machine's jupyter notebook. 
