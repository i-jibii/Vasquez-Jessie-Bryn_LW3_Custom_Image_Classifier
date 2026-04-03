# Laboratory Work 3 Activity — Building a Custom Image Classifier with
TensorFlow Using Personal Image Datasets from Google Drive

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1yZImS_Gc4DWplk1FdONKdHfKQ2z-pSo9?usp=sharing)

# **Guide Questions (Student Reflection & Explanation)**

### **1. Dataset Preparation**
*   **How did you organize your dataset in Google Drive?**  
    I organized the moss species into a main folder named `ImageDataset`. Inside that folder, I created 20 subfolders, one for each specific species (e.g., "Pincushion moss," "Broom moss," "Peat moss"). I placed the resized images directly into their respective folders to make sure the model could associate each image with the correct label.

*   **Why is folder structure important for TensorFlow image loading?**  
    The folder structure acts as the labeling system for the AI. When TensorFlow runs the `image_dataset_from_directory` function, it automatically reads the folder names and assigns them as the "Class Names." Without this structure, the model wouldn't know which images belong to which species of moss.

---

### **2. Model Training**
*   **What is the role of convolutional layers in image classification?**  
    Convolutional layers act like "pattern finders." They scan the images to identify key features like the texture of the moss, the shape of the leaves, or the color patterns. The first layers find simple things like edges, while deeper layers recognize complex structures that make each moss species unique.

*   **Why do we split data into training and validation sets?**  
    We split the data to prevent the model from just "memorizing" the training photos. The **training set** (80%) is what the model learns from, and the **validation set** (20%) is a "practice test" with images it hasn't seen before. This tells us if the model actually understands moss species or if it's just repeating what it memorized.

---

### **3. Performance Analysis**
*   **What accuracy did your model achieve?**  
    My model achieved an impressive **Validation Accuracy of 96.90%**. This means the AI was able to correctly identify the moss species in almost every single test case shown to it during evaluation.

*   **How did the number of images affect the model’s performance?**  
    Having a large dataset of **6,299 images** was the main reason for the high accuracy. With over 300 images per species, the model had enough examples to learn what each moss looks like from different angles and in different lighting, which made it much more reliable than a model trained on a smaller dataset.

---

### **4. Critical Thinking**
*   **What challenges did you encounter while using your own dataset?**  
    The biggest challenge was the **processing time** when trying to train directly from Google Drive. Because my dataset had thousands of images, the "Epoch 1" took a long time to start. I had to ensure my images were properly resized and that the "AUTOTUNE" setting was enabled to help the computer read the data more efficiently.

*   **How can data augmentation improve your model?**  
    Data augmentation helps the model be more "flexible." By randomly flipping or rotating the images, we show the computer that a Pincushion moss is still a Pincushion moss even if it is upside down or zoomed in. This prevents the model from being confused by new, real-world photos that aren't perfectly aligned.

---

### **5. Application**  
*   **Suggest a real-world application for your trained model.**  
    I would suggest a **"Smart Bryology Field Guide."** This could be a tool for researchers or park rangers to quickly identify rare moss species in the wild just by taking a photo, helping with environmental surveys and forest health monitoring.

*   **How can this system be integrated into a mobile or web application?**  
    We can export this model as a "TFLite" file for mobile apps or "TensorFlow.js" for websites. A user could then open their phone's camera in the app, and the model would analyze the live feed in real-time to overlay the name of the moss and the "96.9%" confidence level on the screen.

    
# Activity 3A: Improving and Evaluating a Custom Image Classifier

# **Guide Questions (Student Explanation & Reflection)**

### **Visualization & Overfitting**
1.  **What signs indicated overfitting in your first model?**  
    In the first model, the training accuracy reached almost 100% while the validation loss showed a slight upward "hook" towards the end. This gap, even if small, suggests the model was beginning to memorize the specific pixels of the training folder rather than learning general moss features.

2.  **How did data augmentation affect validation accuracy?**  
    Data augmentation made the training task harder! Although the accuracy numbers dropped from 96.9% to 74.11%, the model is actually much smarter now. It can now recognize moss even if the photo is taken in different lighting, rotated, or zoomed in, which wasn't possible before.

---

### **Model Improvement**
3.  **What is the purpose of dropout layers?**  
    Dropout layers act like a "team exercise" for the model's neurons. By randomly turning off 30% of the neurons during training, it forces the remaining neurons to step up and learn the features themselves. This prevents the model from relying too heavily on any single path and stops "memorization."

4.  **Why does data augmentation improve generalization?**  
    Generalization is the ability to work on photos the model has never seen. By creating "fake" variations of our images (flipping, rotating), we essentially give the model a much larger and more diverse dataset. This teaches the AI that a moss species stays the same regardless of the angle of the camera.

---

### **Performance Comparison**
5.  **Compare accuracy before and after improvements.**  
    **Before:** The model reached a high of 96.9% validation accuracy but was at risk of overfitting to the specific dataset.  
    **After:** The model reached 74.11% validation accuracy. While the number is lower, the model is more reliable for real-world use because it was trained on more difficult, augmented data.

6.  **Which technique contributed most to improvement?**  
    **Data Augmentation** contributed the most to the model's robustness. It expanded our dataset of 6,299 images into thousands of different variations, ensuring the model learned "shapes" and "textures" instead of just "static photos."

---

### **Deployment & Application**
7.  **Why is saving the model important?**  
    Training a high-quality model takes a lot of time and powerful GPU resources. By saving it as a `.keras` file, we can "freeze" the model's intelligence and load it instantly into any app or website later without ever having to run the 15+ minutes of training again.

8.  **How can this model be deployed in a real-world system?**  
    This model can be integrated into a **Mobile Research App** where a scientist in the field can point their camera at a rock, and the app will use this saved model to identify the moss species in real-time. It could also be used in **Automated Ecology Drones** that survey forests to count different plant populations.
