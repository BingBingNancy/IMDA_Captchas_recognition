# IMDA_Captchas_recognition
This is a program for recognizing captchas in an image
Problem formulation: the image is segmented vertically and equally into 5 smaller segments. Each segment corresponds to a character. 
                     The problem of recognizing captchas can be formulated as classifying a segment into a character (0-9,A-Z). This is a multi-class classification problem. 
Steps:
1. upload all   .txt files into colab.
2. split these .txt files into two lists output_file_list and input_file_list. In each list, the .txt file is arranged in increasing order, e.g., input00, input01...input 24
3. I converted the RGB values to a single grayscale pixel value
4. For input_file_list, each .txt, I split it into 5 smaller matrices, where each matrix corresponds to a character. Then, each matrix is flattened into a vector with 360 pixel values.Thus, each input .txt file
   is converted to a matrix with 5x360 dimensions.
5. All input .txt files are processed in the same way and result in the training samples X (125x360)
6. All ouput .txt files form the label list y (125,)
7. Element in y is encoded into integers.
8. Split 80% for training and 20% for testing (100 samples train, 25 samples test)
9. Create train_loader and test_loader
10. Define the Multi-Class MLP Model
11. Create 5 new samples for demonstration
