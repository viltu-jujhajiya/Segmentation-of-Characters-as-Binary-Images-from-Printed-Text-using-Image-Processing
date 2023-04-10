# Segmentation-of-Characters-as-Binary-Images-from-Printed-Text
"Segmentation-of-Characters-as-Binary-Images-from-Printed-Text" is a image processing task. It is useful in reading/copying/recognition of character/word/sentence in a printed document.  

## Working Steps

## (1) Image Pre-processsing: 
      (a) If average intensity of the image is between .50 and .90 then normalize that image 
          else if average intensity of the image is more than or equal to .90 then apply CLAHE (Constrast Limited Adaptive Histogram Equalization). Usually, CLAHE is used to improve contrast.
   ![original](https://user-images.githubusercontent.com/47334614/230946871-c7e59eb4-8b8b-4667-97eb-a14a3065944d.png)



      (b) Binarization: Used Otsu's thresholding method for image binarization for better performance of segmentation algorithms. Before binarization of an RGB image, it is converted to grayscale image.
   ![gray](https://user-images.githubusercontent.com/47334614/230946893-a2adc8d4-4e7c-4fe4-9e03-537d3e0d1bbf.png)

       
## (2) Segmentation: 
     Characters segmentation is done in two steps: 
      (a) Line Segmentation: For line segmentation in printed text, a simple technique works well which is very similar to HPP(Horizontal Projection Profile). Every segmented line is stored in a python list for further steps.
   ![line1](https://user-images.githubusercontent.com/47334614/230943073-ecdc0abb-882c-446f-855b-3bbb261f65ad.png)
   ![line2](https://user-images.githubusercontent.com/47334614/230943081-b1a5e899-3e30-451a-8f2c-fc4c730de473.png)
   ![line3](https://user-images.githubusercontent.com/47334614/230943098-0d9a0c06-6af7-4cf4-b2cd-61fb6e4d905b.png)
   ![line4](https://user-images.githubusercontent.com/47334614/230943112-479aec13-7e7f-431c-9f95-ee7fc1a49a7a.png)

      (b) Character Segmentation: Character Segmentation is done on the segmented lines. Same as line segmentation, a similar method to VPP(Vertical Projection Profile) was used and then every segmented character is stored in a python list.  
   ![characters](https://user-images.githubusercontent.com/47334614/230943291-bfbed75f-2e22-4a6f-b1a1-871475cd5a08.png)

     
## (3) Touching Character Segmentation: m = vertical length of a character, n = horizontal length(width) of a character
                                        if (.80)*m < n: then those two characters are separated.   
                                       
## Results: 
                Single Character Segmentation Accuracy: 164/168
                Double Character Segmentation Accuracy:   4/168
                Triple or more character Segmentation Accuracy: 0/168
                           
      
