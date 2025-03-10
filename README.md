# Federated Learning using CIFAR-10
Implementing federated learning on IoT devices using the CIFAR-10 dataset

---

## Abstract
This is the final project for the Intelligent IoT Systems course taught by Professor Woonghee Lee at Hansung University. Federated learning is emerging as a crucial technology among the numerous users who own IoT devices. It not only ensures personal information protection and data privacy but also serves as a key method for developing advanced AI models based on diverse user data. In this project, the objective is to develop a system that establishes a federated learning environment between a central server and IoT devices, enabling continuous updates and improvements of AI models without transmitting the data stored on individual devices to the central server.

---

## Class Imbalance Problem
<table>
  <tr>
    <td><img src="./image/Label_Distribution.png" alt="Image 1" width="900px" /></td>
  </tr>
</table>

train_partition0 class counts: Counter({0: 2535, 1: 352, 2: 280, 3: 4445, 4: 303, 5: 4086, 6: 4474, 7: 1554, 8: 1125, 9: 5000})

train_partition1 class counts: Counter({0: 2465, 1: 4648, 2: 4720, 3: 555, 4: 4697, 5: 914, 6: 526, 7: 3446, 8: 3875, 9: 0})

test_dataset class counts: Counter({3: 1000, 8: 1000, 0: 1000, 6: 1000, 1: 1000, 9: 1000, 5: 1000, 7: 1000, 4: 1000, 2: 1000})

-> We can check Class Imbalance Problem. We tried to use focal-loss or weightening on small amount data. But, it wasn't work.

---

## Result of final project
<table>
  <tr>
    <td><img src="./image/Results_in_competition.png" alt="Image 1" width="900px" /></td>
  </tr>
</table>
Our result is from Team 1 in Class A. The accuracy was the second highest, and the training time was significantly lower—about 14 minutes and 20 seconds less—than that of the top-ranked team. In terms of training time, it was also the second shortest. Although the model size is relatively large, its training and prediction times demonstrated a satisfactory performance. For FedAvg, there is a rule that everyone must use it identically, so we couldn't modify it.

---

## Our Pipeline
<table>
  <tr>
    <td><img src="./image/Model_pipeline.png" alt="Image 1" width="900px" /></td>
  </tr>
</table>
<table>
  <tr>
    <td><img src="./image/FedAVG_pipeline.png" alt="Image 1" width="900px" /></td>
  </tr>
</table>

We utilized the aforementioned model architecture and training with normal FedAVG. We aimed to achieve better performance by richly extracting local features using a CNN architecture and then employing a ViT to capture global relationships from those features. The results were pretty good.

---

## My Notion
You can check more information at my notion page.

https://rustic-flavor-e48.notion.site/Federated-Learning-using-CIFAR-10-14fe2f945c638064b96cde9255a904d2?pvs=4
