# Vasquez-Jessie-Bryn_LW3_Custom_Image_Classifier

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
