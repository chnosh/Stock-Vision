# Stock-Vision
Stock market forecasting by taking images containing graphs of the stocks as input.

The project is built using Intel oneAPI AI toolkit and is also deployed on cloud using the same environment ("environment.yml"). <br/>
Link: <b><u>https://chandrahas-b-stockvision-final-noz83u.streamlit.app/ </u></b>

## Adaptibility and Impact:
  Conventional forecasting techniques for predicting stock movement rely heavily on tabular data. In an effort to explore new approaches to this problem, our team has developed a novel method that involves using image processing techniques to extract graphs from images. By analyzing these graphs, we can forecast future stock values for the next 100-200 periods, providing users with valuable insights into stock investment.  <br/> <br/>
  Our approach represents a departure from traditional forecasting methods and allows us to extract information from visual data that was previously inaccessible. This unique method provides users with a more holistic understanding of stock movement and can help make informed investment decisions. <br/>



https://user-images.githubusercontent.com/84665480/226104730-b15ef19b-dfd7-4624-bf2f-9cdd513cd89b.mp4



## Code:
  The forecasting model was developed using an AI toolkit that provided optimizations to build deep learning models. After experimenting with multiple models and architectures, the best model was identified as a combination of Conv1d and LSTM layers.  <br/><br/>
  The dataset used in the project consisted of graph images that were hand-picked by identifying the relevant stocks and taking screenshots of them. Each image contained a graph, which was then converted into tabular data using bit-masking and other pre-processing techniques. The dataset comprised around 210 images, all of which contained continuous graphs. These graphs were broken down into individual points and used for generating training set, resulting in a total of approximately 1.2 million unique records.
  
  
## Design:
  After experimenting with multiple models and architectures, a combination of multiple Conv1D and LSTM layers without skip connections, was found to perform well in achieving a good Mean Squared Error score.  
  The oneAPI AI toolkit provided optimizations for the TensorFlow module, which improved the speed of training without sacrificing precision. This optimized toolkit allowed for efficient and accurate training of the model with improved performance.  
  ![image](https://user-images.githubusercontent.com/84665480/225654048-566e8770-8884-4b4a-b067-f9415a91b233.png)
The model was trained with aprroximately 150k trainable parameters. With this architecture, the model can generate accurate results in a shorter time and is highly scalable. It was trained on 60-70 trending stocks of 2022-23, and its performance can be improved by training it on additional stocks. This scalability makes the model flexible and adaptable to future changes in the stock market.
## Usability:
  The project was aimed to be used on a daily basis to assist users in understanding the graph movement. This can also garner interest in new users to invest in stocks and help them understand the graph movements and make wise decisions while investing.
  The project has covered functionalities such as image processing for extracting graphs and can forecast around 150 values. 
  
## Prototype build:
 The project has been implemented with several functionalities that make it a viable tool for daily stock forecasting. As a baseline prototype, it can serve as the foundation for creating a more robust product. With its various functionalities, the project represents a significant step towards the development of a reliable and comprehensive stock forecasting tool. Its potential to be further developed and refined makes it an exciting prospect for investors and analysts seeking to make informed decisions in the stock market.
 
## Note:
  The model was developed on various environments due to the large number of epochs required for convergence. Some epochs were trained on the dev-cloud until resource limits were reached, while others were trained on local systems in optimized and non-optimized Intel oneDNN environments. Inference time was measured to compare the performance between the optimized and non-optimized training speeds in these environments.<br/><br/>
  <b>Without oneAPI optimization</b>: (200 epochs with 150 images)<br/>
    Time taken to train the model:	<b>6985.663848876953 s</b> <br/>
    Time taken to run the notebook:	<b>6991.916996240616 s</b> <br/>
    
  <b>With oneAPI optimized oneDNN environment</b>: (100 epochs with 100 images)<br/>
    Time taken to train the model:	 <b>2402.2500801086426 s</b><br/>
    Time taken to run the notebook:	 <b>2408.7944316864014 s</b><br/>
  As we can see, oneDNN optimization helps the model to train faster(almost 50% faster) and optimizes the CPU calculations without having a great impact on the accuracy.
 <br/><br/>
 <i>Steps to run the above project locally:</i> <br/>
 Clone the repository.
 ```
 git clone https://github.com/Chandrahas-B/Stock-Vision
 ```
 <br/> Create and activate the conda environment by replacing <env_name> with appropriate name. <br/>
 ```
 conda create --name <env_name> --file environment.yml
 conda activate <env_name>
 ```
 <br/> To run the streamlit application locally, use the following command:
 ```
 streamlit run final.py
 ```
 
