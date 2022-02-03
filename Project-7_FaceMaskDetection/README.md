https://user-images.githubusercontent.com/67855083/152309092-d847927d-7679-4d1a-a65e-d0397541e67c.mp4

In this project, I have done detection with three different sorts:
1) CNN with preprocessing:

   --Data Preprocessing:
        collect the data in the datapath, categorize with listdir and labelling these categories.
        Take specific image size for standard resize of all images, now set to read every image in the folder path of categories.
        Thereafter try the method to convert to grey, resize, append into data list and category into target list. exception method is to except the corrupt images 
        Exception method to except the images that are failed to detect or corrupted ones to avoid error 
        now normalize the appended data variables and reshape with a four-dimensional image, also convert to array the target variables
        Keras. utils are applied to convert the target into categorical variables
        save the data and variables which are processed.
        
   --Training the CNN:
        load the saved data and variables, import the required Keras and TensorFlow packages to build CNN neural network
        Build the model with sequential of Conv2D, input shape, ActivationFunction, Pooling, Flatten, Dropout and Dense layers
        Compile the model with optimizer Adam, loss as categorical_crossentropy and metics = accuracy.
        split the data and check with Modelcheckpoints then fit into a model
        Now check the accuracy and the  loss of the model for evaluation
        
    --Detecting Mask with open cv:
        load the model and get haar cascade feature classifier algorithm in XML file
        start the video capture and make label dict and colour dict
        In while loop continues captures, convert capture images to grey and detect faces with Haarcascade classifier
        Now the parameters of faces will spot the face area and resize, normalize, reshape the variables of it. Using a built model predict the images
        That Prediction 0,1 has to label it as a mask and no mask. create a bounded rectangle for visual detection in OpenCV webcam or file of image, videos, put text over it 
        with the font to understand us
        Now show the image and release the capture
        
        
2) Machine Learning detection:
 
     import basic packages and get haar cascade classifier algorithm then capture the video and build open cv process same as previously but to make conditions of required            specific images to collect data synthetically from our face. here run two loops of dataset one is without mask and other is with mask and then save this two data
     Now load this manually collected data which are saved and reshape their dimensions to two-dimensional rows and columns concatenate the data which are with mask and without      mask data in one data list as rows concatenation, then labelling it for the first loop is without mask and second is with the mask.
     import the ML classification packages and do train test split the dimensional reduction with PCA method for higher columns which is hard for computation power.
     Apply the ML model that is imported to the collected data and also labels the target, color_dict
     now build the same open cv process and few more lines to predict the result with the ml model in the final process
     The same previous code to bound rectanglea and put text and release the capture.     
       
3) Face Mask Detection direct cvv:

      Install the required packages, do the DataAugmentation, Read the test directory images,Build the model,compile the model,fit the model,save and load the model
      get the haar cascade classifier,label it , then same old open cv process, apply haarcascade algorithm,bound rectangle,putText,release the capture.
      
       

       
       
       
       
       
       
       
       
       
       
       
       
       
       
       
       
       
