# VPN-IP-Address-Classification
In today's digital era, safeguarding against cyber threats is imperative. Our focus is on discerning hidden identities behind VPN/Proxy IP addresses, a tactic commonly used by malicious actors to evade detection.

Our aim is to build precise predictive models that can accurately differentiate IP addresses routed through VPN/Proxy services from legitimate ones. This classification is pivotal in fortifying cybersecurity measures by identifying potential threats more effectively.
![image](https://github.com/user-attachments/assets/beae05ae-b5ce-43a1-b4f8-2e30909af3a6)

The dataset contains “61629685” data points and the below columns:
![image](https://github.com/user-attachments/assets/39d5d852-c528-4e4d-b1eb-ee1edfc7b133)

![image](https://github.com/user-attachments/assets/74c28b6d-d791-4952-8b05-e3a0206bd028)

![image](https://github.com/user-attachments/assets/fcfda75d-f195-453e-b194-d8687a4d013e)
![image](https://github.com/user-attachments/assets/6d4df8eb-8d2b-47c5-9e60-5bc8745b8d39)
![image](https://github.com/user-attachments/assets/af34178a-d2e9-4b3d-b8fe-2d1399453b2d)

After EDA we decided to only go with 4 main features:
Attack Service Type: database, ftp, http, pop3/imap, sip, smb, ssh, tcp, telnet, unknown, windows. (One hot encodings)
Attack Type: bruteforce, crawl, exploit, scan, spam, unknown (Distributions)
Open Ports: port_22, port_443, port_7777, port_80 (One hot encodings)
Number of open ports (Sum)
This resulted in 23 columns including label column.
![image](https://github.com/user-attachments/assets/9c395c15-5dbe-4c81-a223-eeb232e5de6b)

To accurately classify whether an IP address is associated with a VPN or Proxy service, we used three algorithms:Support Vector Machine:SVM is effective in defining complex decision boundaries, crucial for distinguishing VPN and non-VPN traffic, which might exhibit intricate patterns.
Random Forest Classifier:RF, being an ensemble method, is robust and less prone to overfitting. This is crucial in capturing varied patterns present in VPN and non-VPN data.
Neural Networks: NN excels in capturing intricate patterns and relationships within data, making it suitable for tasks with spatial or sequential structures.

Support Vector Machines (SVM) is a powerful supervised machine learning algorithm used for classification and regression tasks. 
It works by finding the optimal hyperplane that separates data points of different classes in a high-dimensional space.


In our project, we employed SVM for binary classification tasks. The model was configured with a linear kernel, making it suitable for our dataset. We utilized a balanced class weight to address imbalances in the data, and the random state was set to ensure reproducibility.
![image](https://github.com/user-attachments/assets/8d010407-854f-43cc-bd52-a7dc06966246)

Random Forests: Utilized GridSearchCV to systematically explore a range of hyperparameters for optimal model performance.

Neural Networks: We have used a model with 3 hidden layers and output layer with 1 neuron.
ReLU activation for hidden layers and sigmoid activation for the output layer.
Loss function is “Binary Cross Entropy” loss.
Model trained for 40 epochs with 128 batch size.

The Security Engine seamlessly communicates with the backend, contributing vital data to our trust and reputation system. The current challenge involves enhancing threat detection by building a predictive model to classify whether an IP address originates from a VPN or Proxy service. Given the prevalence of malicious users using such services for identity anonymization, this classification is pivotal for fortified cybersecurity.




