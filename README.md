#to make this project work, you will need the basic prerequisites of imagenet, python, wget, and linux installations

run this command: wget (whatever data source you want to use(NEEDS TO BE A COPY-PASTED LINKED FROM A DOCUMENT))
*make sure there is atleast 100s of images for the training to go off ofmake sure python is installed and run, python3 train.py --model-dir=models/jetsonproject data/jetsonproject
you will need a docker container (script: ./docker/run.sh ) 
make sure training gets you to atleast 4-5 epochs for the image to become accurate
where then you run scrip: "python3 onnx_export.py --model-dir=models/jetsonproject
use "ls" to confirm your script called "onnx"
set your two net and dataset models:
NET=models/jetsonproject
DATASET=data/jetsonproject
run: imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/"whatever category you want"/"whatever image you want" 0.jpg
Use this command to verify the image, and its categorization on a seperate terminal: 
scp <nanousername>@192.168.55.1:/home/<nanousername>/jetson-inference/python/training/classification/cat.jpg C:\Users\<hostusername>\Desktop
