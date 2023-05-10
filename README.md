# Prepare Data
This project used many datasets.It contains public data and private data.
- test data

    test data is only used to test the program correction. 
- your own data
    
    You can use your own data, which must satisfy some requirements, the structure of data directory is as follows.
    
    ```
    - data
        - dataset_name your dataset name, which you can define it by yourself
            - datas.h5 this file includes your genotype data, where the first column should represent id 
            number, and the others should be genotype data
            - labels_*.h5 this file includes your label data, where the first column should be the id number,
            and the others should be the labels corrsponding to id number. The `*` repersents that you can
            place different labels in your directory and you can define every labels data's name.
    ```