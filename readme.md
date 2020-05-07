
Sports classifier created on top of pytorch using the fastai library.
The deployed model can be used at: 
http://sports-img-classifier.appspot.com/

The classifier was trained using the sports data set by  Li-Jia Li and Li Fei-Fei as part of their paper What, where and who? Classifying event by scene and object recognition . IEEE Intern. Conf. in Computer Vision (ICCV). 2007. The dataset contains images of 8 sports event categories: rock climbing, badminton, bocce, croquet, polo, rowing, sailing and snowboarding.

The images also contain information about the difficulty of the human subject judgment as well as distance of foreground objects, however these are not used in my experiment.


To deploy the model, I first exported the trained model from fast ai. I then made use of the starter pack available at the following link: https://course.fast.ai/deployment_google_app_engine.html. Note however that in the starter pack, they make use of a pth file (contains the models weights) while I had saved a pkl (pickle) file of my trained model. Some changes had to be made to the server.py file to upload the proper file type to the models directory.

Running the deployment locally:
Can be done by running python app/server.py server

Note that I created a virtual env to install all needed packages and used the command below to install the versions of torch and torchvision that I used to train my model.
# to setup torch and torchvision on windows
pip install torch===1.4.0 torchvision===0.5.0 -f https://download.pytorch.org/whl/torch_stable.html


# to get download link
This will provide you a download link for your saved model, one that will initiate a download automatically of the model.
https://rawdownload.now.sh/

Deploying to google cloud
1. Create a new project
2. Make sure to activate google cloud shell (I had to do this manually)
3. In the terminal window that pops up, run
---
gcloud app create
---
4. Select the geographical location nearest to you
5. clone your repository that contains your app, the requirements file and so on.
---
git clone https://github.com/Jeremie-Gabor97/sports-img-classifier
---
6. cd into your project
7. Deploy app to google engine. Enter Y when prompted
---
gcloud app deploy
---
8. After several minutes, your project should be available at the "target url:" specified in the terminal window
