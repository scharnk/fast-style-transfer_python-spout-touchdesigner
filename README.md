# fast-style-transfer_python-spout-touchdesigner
This repository is a tensorflow implementation of fast-style transfer in python to be sent into touchdesigner. To talk to both programs Spout is required. Commands are written for windows10, linux/mac commands will vary slightly. This repo is designed to be a fully packaged tutorial to get everything running for webcam style transfer video in touchdesigner.

<h2>Dependencies</h2>
<h3>Set Up for Windows10:</h3>

<ul>
  <li>Install python 3.5.1 <a href="https://www.python.org/downloads/release/python-351/" rel="nofollow">here</a></li>
  <li>Visual Studio Community 2015 <a href="https://go.microsoft.com/fwlink/?LinkId=532606&clcid=0x409" rel="nofollow">here</a>
  <li>CUDA8.0 (make sure to uninstall any other versions of CUDA)<a href="https://developer.nvidia.com/cuda-80-ga2-download-archive" rel="nofollow">here</a></li>
    <ul>
      <li>Run exe file, follow prompts</li>
    </ul>
  <li>CUDA8.0 patch <a href="https://developer.nvidia.com/cuda-80-ga2-download-archive" rel="nofollow">here</a></li>
  <li>cuDNN 5.1 <a href="https://developer.nvidia.com/rdp/cudnn-archive" rel="nofollow">here</a>
    <ul>Extract & Paste/drop files manually into Program Files/CUDA/8.0/*respective folders* (i.e. bin, input, etc)</ul>
  </li>
  <li>Restart computer</li>
  <li>Double check CUDA_PATH exists in path--Type environment variable in search</li>
  <li>Tensorflow 1.2.0
    <ul><code>Python -m pip install tensorflow_gpu==1.2.0</code></ul>
    <ul>(may have to upgrade pip first before this will run)</ul>
  </li>
  <li>Opencv 3.3.0.9
    <ul><code>Pip install opencv-python==3.1.0</code></ul>
  </li>
  <li>pygame</li>
    <ul><code>python -m pip install pygame</code></ul>
  <li>PyOpenGL</li>
    <ul><code>python -m pip install PyOpenGL==3.1.0</code></ul>
  <li>scipy</li> 
    <ul>python -m pip install scipy==1.0.0</ul>
  <li>numpy</li> 
    <ul>python -m pip install numpy==1.13.1</ul>
  <li>pillow (PIL)</li> 
    <ul>python -m pip install pillow</ul>
  <li>imageio</li> 
    <ul>python -m pip install imageio (I used 2.5.0)</ul>
  <li>matplotlib</li> 
    <ul>python -m pip install matplotlib (I used 3.0.3)</ul>
  <li>scikit-image</li>
    <ul>python -m pip install scikit-image (I used 0.15.0)</ul>
  <li>Download the pretrained vgg19 imagenet from <a href="http://www.vlfeat.org/matconvnet/models/imagenet-vgg-verydeep-19.mat">here</a></li>
    <ul>Place it in same directory in a folder named 'pre_trained_model'</ul>
  <li>Download MSCOCO train2014 dataset (*12GB*) from <a href="http://msvocds.blob.core.windows.net/coco2014/train2014.zip">here</a></li>
    <ul>Make sure full folder downloads (crdownload file = incomplete)</ul>
    <ul>I'd recommend keeping the downloads tab open, check it periodically and click resume if it has been interrupted. Do NOT close the browser.</ul>
    <ul>When complete, make sure folder is named 'train2014'</ul>
  <li>Download and install Spout <a href="http://spout.zeal.co/">here</a></li>
  <li>(OPTIONAL) Pre-trained style-model from hwalsuklee <a href="https://mega.nz/#F!VEAm1CDD!ILTR1TA5zFJ_Cp9I5DRofg">here</a></li>
</ul>

<h2>Example Usage:</h2>
<h3>Style-transfer</h3>
<h4>To run from terminal set directory to project location & set required parameters: </h4>
<code>cd C:\Users\_______\Documents\fast-style-transfer_python-spout-touchdesigner</code>

<h4>To test style transfer:</h4>
Before you can test style transfer you either have to download a pre-trained style-model (above) or you have to train a model yourself (next section).<br>

<code>python run_test.py --content content/imageyouwantstylized.jpg --style_model fast_neural_style/rain_princess.ckpt --output stylizedimage.jpg</code><br>

Required parameters:<br>
--content: Filename of the content image. Default: content/female_knight.jpg <br>
--style-model: Filename of the style model. Default: models/wave.ckpt <br>
--output: Filename of the output image. Default: result.jpg<br>
Optional parameter:<br>
--max_size: Maximum width or height of the input images. None do not change image size. Default: None<br>

<h4>To train models:</h4>
<code>python run_train.py --style style/stylesourceimage.jpg --output modelname --trainDB train2014 --vgg_model pre_trained_model</code>

Required parameters:<br>
--style: Filename of the style image. Default: images/wave.jpg<br>
--output: File path for trained-model. Train-log is also saved here. Default: models<br>
--trainDB: Relative or absolute directory path to MSCOCO DB. Default: train2014<br>
--vgg_model: Relative or absolute directory path to pre trained model. Default: pre_trained_model<br>

Optional :<br>
--content_weight: Weight of content-loss. Default: 7.5e0<br>
--style_weight: Weight of style-loss. Default: 5e2<br>
--tv_weight: Weight of total-varaince-loss. Default: 2e2<br>
--content_layers: Space-separated VGG-19 layer names used for content loss computation. Default: relu4_2<br>
--style_layers: Space-separated VGG-19 layer names used for style loss computation. Default: relu1_1 relu2_1 relu3_1 relu4_1 relu5_1<br>
--content_layer_weights: Space-separated weights of each content layer to the content loss. Default: 1.0<br>
--style_layer_weights: Space-separated weights of each style layer to loss. Default: 0.2 0.2 0.2 0.2 0.2<br>
--max_size: Maximum width or height of the input images. Default: None<br>
--num_epochs: The number of epochs to run. Default: 2<br>
--batch_size: Batch size. Default: 4<br>
--learn_rate: Learning rate for Adam optimizer. Default: 1e-3<br>
--checkpoint_every: Save-frequency for checkpoint. Default: 1000<br>
--test: Filename of the content image for test during training. Default: None<br>
--max_size: Maximum width or height of the input image for test. None do not change image size. Default: None<br>

  <!-- <li><code></code></li>
  <li><code></code></li>
</ul>
<code></code><code></code> -->
<h3>Spout Usage</h3>
<h4>To test spout:</h4>
Start with <code>python spout_hello.py</code> should get 'Hello, from c++ dll!'<br>

Next try <code>python spout_receiver_example.py</code> and <code>python spout_receiver_example.py</code><br>
When these are working the receiver should open a black window, and the sender should show a rotating cube.<br>

<h4>To run style transfer from webcam video and view in touchdesigner:</h4>
Open touchdesigner file (spout.3.toe)<br>
Make sure videodevin1 is active (toggle=on), and syphonspoutin1 is set to the correct sender and toggle=on<br>
Make sure sender name in spout_NST_receiver_sender.py matches that in Touch<br>
Touchdesigner should be open when you run: <code>python spout_NST_receiver_sender.py</code><br>
If working, you should see the stylized video feed from the style model you've selected<br>

<h2>Contributors</h2>

<h2>Acknowledgements</h2>
Fast-style transfer is based on this repo: https://github.com/hwalsuklee/tensorflow-fast-style-transfer <br>
Spout for Python was based on this repo: https://github.com/spiraltechnica/Spout-for-Python <br>
Some set up/dependencies were from Grant Watson's fastyle transfer repository here: https://github.com/ghwatson/faststyle <br>