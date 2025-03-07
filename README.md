# Hand_Written Digit App
### This is a hand written digit recognization app where users draw digit(s) of arabic numerals and get back what the digit(s) is. Users draw the digits on html canvas holding their mouse and release the mouse as soon then they are done drawing the single digit, then click the predict button and receive the predicted digit(s). The digit identification process involves drawing the digit on the canvas, then when user click the predict button the entire content of the canvas is converted to and send as base64 encoding string. As soon as the POST request to the flask end point is made the flask app will prepare the received image to suit the pre-trained Machine Learning(ML) model. Since the ML model is trained with MNIST dataset it shall receive the digit as such.The image has to pass through different preprocessing prior to idientification that involces corrections, convertion to grey scale, convertion to to binary, Finding the contour, filtering out non-digit like regions, extracting regions containing digit, dilateing the digit, and resizing the digit. Once those steps are completed the ML can reconize the digits.

### Demo
#### A sample demo is presented here
![Demo GIF](docs/assets/demogif/demo.gif)

### Training
#### The training of the ML model is an iterative process that involves progressively increasing the training dataset using the MNIST dataset, which contains 60,000 handwritten digits collected from American students. In the first few iterations, the model was trained with a small dataset and its performance was measured by feeding it new handwritten digits it hadn't encountered before. If the model's performance was not satisfactory, it would be retrained with a larger dataset. This model is trained with the entire 60,000-digit dataset and performs very well in identifying digits. The only setback is that the preprocessing of the digits is not perfect, which sometimes causes issues.

### Libraries Used
#### Powerful python libraries known for image processing and deep learning are used in this project to mention a few of them like Tensorflow and keras for deep learning numpy tp enables operations like matrix transformations, filtering, resizing, and color space conversions, pillow and open CV are used.

### Deployment
##### The app is deployed on a local Kubernetes cluster called Minikube. Since it's a lightweight version of Kubernetes, it allows users to easily set up a development environment for testing and experimenting with Kubernetes without needing a full-fledged Kubernetes cluster. For this particular project, Docker Desktop is used to allow users to build, run, and manage Docker containers and images locally. The process of deploying this application involves preparing a Dockerfile with a Python 3.9 base image, creating a YAML file for deploying the pods, and choosing NodePort to access the app from outside the Kubernetes cluster. To explore more about Minikube and kubectl (the command-line tool used to interact with a Kubernetes cluster), follow the links below

[minikube](https://minikube.sigs.k8s.io/docs/start)

[kubectl](https://kubernetes.io/docs/reference/kubectl/)