# 🌿 Thermal Image Classification - Paddy Leaf Health Detection 🌡️

This project aims to classify thermal images of **paddy leaves** into healthy and diseased categories using **transfer learning**. We explored and compared three state-of-the-art pretrained deep learning models—**MobileNetV2**, **ResNet50**, and **InceptionV3**—under various training configurations. This work contributes to a broader effort in early detection of crop diseases using AI and is part of an **IEEE research paper**.

---

## 📁 Dataset

We used the thermal image dataset available on Kaggle:

**🔗 Dataset**: [Thermal Images of Diseased and Healthy Leaves - Paddy](https://www.kaggle.com/datasets/sujaradha/thermal-images-diseased-healthy-leaves-paddy)

- Number of Classes: **6**
- Image Type: **Thermal RGB Images**
- Categories include: Different health conditions of paddy leaves.
- Resized Input Shapes:
  - **224x224x3** for MobileNetV2 and ResNet50
  - **299x299x3** for InceptionV3

---

## 🧠 Models Used

We applied **transfer learning** using pretrained models from `tf.keras.applications`. All models use:
- `include_top=False` to remove default classifier
- Global average pooling
- Additional fully connected layers and dropout
- Softmax output layer for 6-class classification

| Model        | Input Size | Notable Traits                          |
|--------------|-------------|------------------------------------------|
| MobileNetV2  | 224x224x3   | Lightweight, good for real-time apps     |
| ResNet50     | 224x224x3   | Deeper network, handles complex patterns |
| InceptionV3  | 299x299x3   | Balanced model, handles varying features |

---

## ⚙️ Training Details

Each model was trained using different **optimizers** and **learning rates** to assess their performance. The models were trained for **5, 10, 15, and 20 epochs**.

### 🛠 Optimizers Used
- `Adam`  
- `SGD` (with momentum)  
- `RMSprop`  

### 🧪 Learning Rates
- `0.00001`  
- `0.0001`  
- `0.001`  

### 🧾 Other Settings
- Loss Function: `Categorical Crossentropy`
- Metrics: `Accuracy`
- Callbacks: `EarlyStopping`, `ModelCheckpoint`, `TensorBoard`

---

## 📊 Model Performance

A detailed performance comparison is available in the `Model_Performance_Report.pdf` file in this repository.

Metrics compared:
- Training and Validation Accuracy
- Loss curves
- Generalization performance
- Convergence speed with different optimizers

---

## 🗂️ Repository Structure

| File/Folder                         | Description                                        |
|------------------------------------|----------------------------------------------------|
| `MobileNetV2_Thermal.ipynb`        | Training notebook for MobileNetV2                  |
| `ResNet50_Thermal.ipynb`           | Training notebook for ResNet50                     |
| `InceptionV3_Thermal.ipynb`        | Training notebook for InceptionV3                  |
| `Model_Performance_Report.pdf`     | Model comparison report with training details      |
| `README.md`                        | Project documentation (this file)                  |

---

## ▶️ How to Run

1. Clone this repo:
   ```bash
   git clone https://github.com/your-username/thermal-leaf-classification.git
   cd thermal-leaf-classification

## 💡 Key Insights
InceptionV3 with Adam at a lower learning rate offered better generalization.
MobileNetV2 was fastest to train and is ideal for deployment on low-resource devices.
ResNet50 achieved competitive accuracy but required careful tuning.

## 📚 Research Contribution
This project contributes to ongoing research in:

Precision agriculture using thermal imaging , Transfer learning for plant disease detection , Optimizer and learning rate effects on model convergence
📄 This work is part of an IEEE research paper.
📬 For collaboration or citation: rijeshkrishna7910@gmail.com

## 📜 License
This project is licensed under the MIT License.
You are free to use, modify, and distribute the code for both academic and commercial use.

## 🙌 Acknowledgements

🧠 Sujaradha for the thermal leaf dataset
🛠️ TensorFlow & Keras teams for the pretrained model architectures
☁️ Google Colab for cloud-based model training
🎓 IEEE for providing the platform for research publication
