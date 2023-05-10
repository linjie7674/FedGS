FedGS: Genomic Selection with Federated Learning
---
​The program 'fedgs' can be used to perform genomic selection with our proposed federated learning algorithm. In this program, phenotypes of your own data can be predicted using our algorithms. The effectiveness of FedGS has been demonstrated on a wide range of datasets, both simulated and real-world.

# Installation
## Docker Installtion
Go to [docker website](https://www.docker.com/) and download the version satisfying your machine.
## FedGS Docker image installation and quickly start
```bash
docker pull linjie7674/fedgs
docker run -it --federated False --genotype test 
```
**Note:**Test data is only used to test the program correction, and doesn't have any meaning. If the above commands are excuted correctly, your installation is successful.

# Prepare Data
This project used many datasets.It contains public data and private data.
- test data

    test data is only used to test the program correction. 
- your own data
    
    You can use your own data, which must be orginized by the follow strcuture.
    
    ```
    - data
        - dataset_name your dataset name, which you can define it by yourself
            - datas.h5 this file includes your genotype data, where the first column should represent id 
            number, and the others should be genotype data
            - labels_*.h5 this file includes your label data, where the first column should be the id number,
            and the others should be the labels corrsponding to id number. The `*` repersents that you can
            place different labels in your directory and you can define every labels data's name.
    ```

# Run on your own data
```bash
docker run -it -v {host directory of your own data}:/fedgs/data --federated True --genotype {local dataset name} --label_suf {local label suffix} --fed_genotyp {others dataset name} --fed_label_suf {others label suffix}
```

- genotype: your local dataset directory name in data directory
- label_suf: your local label suffix you want use 
- fed_genotype: others dataset directory name, which will be federated learning with your local data.
- fed_label_suf: others dataset label suffix you want use
