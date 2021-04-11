# Fill Station Quality AI

## Use Case

- Ability to use Vision based AI to detect fill color to detect quality of the product
- For Base class we have 3 colors
    - Red
    - Blue
    - Yellow
- Goal is for students to build various color combination and build model
- Also in real world gives the ability to create new model and deploy faster in manufacturing floor
- Also allows the model creation to understand the environment where it predicts
- Take pictures using cell phone
- Use Azure cognitive custom vision to tag the image and build model in 1 hour
- Export the model and deploy to AI @ Edge device and test
- We use transfer learning with 25 to 100 images for each object or classes

## Architecture

![alt text](https://github.com/balakreshnan/csitestbedai/blob/main/images/testbedAI.jpg "Service Health")

## Pre-Requsitie

- Azure Account
- Azure IoT Hub
- Azure ADLS gen2
- Azure Cognitive Services - Custom Vision
- Azure Synanpse workspace - for Big data
- Azure Stream Analytics
- Power BI
- Azure Percept provision with DPS and Device update service, Studio

## Steps

- From the phone download the pictures
- Download the photos to local laptop
- Images are uploaded in the images directory in this repo
- Images are zipped
- I am using sample1.zip
- Unzip the file
- Go to https://customvision.ai
- Create a new project
- Select Object detection
- Select Compact Version V2

![alt text](https://github.com/balakreshnan/csitestbedai/blob/main/images/testbedAI-1.jpg "Service Health")

- Our goal is here to run the inference in AI @ edge device
- Upload the images
- Create Tags

![alt text](https://github.com/balakreshnan/csitestbedai/blob/main/images/testbedAI-2.jpg "Service Health")

- Tag them with Red, Blue and Yellow Fill

![alt text](https://github.com/balakreshnan/csitestbedai/blob/main/images/testbedAI-3.jpg "Service Health")

![alt text](https://github.com/balakreshnan/csitestbedai/blob/main/images/testbedAI-4.jpg "Service Health")

- Train the mode

![alt text](https://github.com/balakreshnan/csitestbedai/blob/main/images/testbedAI-5.jpg "Service Health")

- Wait for Train to complete

![alt text](https://github.com/balakreshnan/csitestbedai/blob/main/images/testbedAI-6.jpg "Service Health")

- Test the model

![alt text](https://github.com/balakreshnan/csitestbedai/blob/main/images/testbedAI-7.jpg "Service Health")

- Export as Vision AI Kit
- Move the model zip to blob container
- Go to IoT Hub and select the ai camera to update
- select vision module and module twin
- update the blob URL
- wait for model to deploy in edge