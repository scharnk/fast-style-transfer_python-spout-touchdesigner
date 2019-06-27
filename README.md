# fast-style-transfer_python-spout-touchdesigner
This repository is a tensorflow implementation of fast-style transfer in python to be sent into touchdesigner
To talk to both programs Spout is required. Commands are written for windows10, linux/mac commands will vary slightly.

<h2>Dependencies</h2>
<h3>Style-Transfer Directions/Set Up for Windows10:</h3>

<ul>
  <li>Install python 3.5.1 <a href="https://www.python.org/downloads/release/python-351/" rel="nofollow">here</a></li>
  <li>Visual Studio Community 2015 <a href="https://go.microsoft.com/fwlink/?LinkId=532606&clcid=0x409" rel="nofollow">here</a>
  <li>CUDA8.0 <a href="https://developer.nvidia.com/cuda-80-ga2-download-archive" rel="nofollow">here</a></li>
    <ul>
      <li>Run exe file, follow prompts</li>
    </ul>
  <li>CUDA8.0 patch <a href="https://developer.nvidia.com/cuda-80-ga2-download-archive" rel="nofollow">here</a></li>
  <li>cuDNN 5.1 <a href="https://developer.nvidia.com/rdp/cudnn-archive" rel="nofollow">here</a>
    <ul>Extract & Paste/drop files manually into Program Files/CUDA/8.0/*respective folders* (i.e. bin, input, etc)</ul>
  </li>
  <li>Double check CUDA_PATH exists in path--Type environment variable in search</li>
  <li>Tensorflow 1.2.0
    <ul><code>Python -m pip install tensorflow_gpu==1.2.0</code></ul>
    <ul>(may have to upgrade pip first before this will run)</ul>
  </li>
  <li>Opencv 3.3.0.9
  <ul><code>Pip install opencv-python==3.1.0</code></ul>
  </li>
  <li>Restart computer</li>
</ul>

<br>
<h2>Downloads</h2>
<ul>
  <li>Download the pretrained vgg19 imagenet from <a href="http://www.vlfeat.org/matconvnet/models/imagenet-vgg-verydeep-19.mat">here</a></li>
      <ul>
        <li>Place it in same directory in a folder named 'pre_trained_model'</li>
      </ul>
  <li>Download MSCOCO train2014 dataset (*12GB*) from <a href="http://msvocds.blob.core.windows.net/coco2014/train2014.zip">here</a></li>
  <li>Download and install Spout <a href="http://spout.zeal.co/">here</a></li>

</ul>
<br>

<h2>Example Usage:</h2>

<h4>To run from terminal set directory to project location & set required parameters: </h4>
<code>cd C:\Users\_______\Documents\fast-style-transfer_python-spout-touchdesigner</code><br>

<h4>To test style transfer:</h4>
Before you can test style transfer you either have to download a pre-trained style-model (hwalsuklee has some available <a href="https://mega.nz/#F!VEAm1CDD!ILTR1TA5zFJ_Cp9I5DRofg">here</a>), or you have to train a model yourself (next section).
<code>python style.py </code>

<h4>To train models:</h4>
<code></code>



<h4>To test spout:</h4>
Start with <code>python spout_hello.py</code> should get 'Hello, from c++ dll!' <br>
Next try <code>python spout_receiver_example.py</code> and <code>python spout_receiver_example.py</code><br>
May need to install pygame and OpenGL:
<ul>
  <li><code>python -m pip install pygame</code></li>
  <li><code>python -m pip install PyOpenGL</code></li>
  <li><code></code></li>
  <li><code></code></li>
</ul>
When these are working the receiver should open a black window, and the sender should show a rotating cube.
<code></code><code></code>

<h4>To run style transfer from webcam video and view in touchdesigner:</h4>
Open touchdesigner file (spout.3.toe) and make sure your webcam is streaming (active=on) and on the node below (1st of second row) make sure syphon spout in is set to the correct sender and active=on
Make sure sender name in spout_NST_receiver_sender.py matches that in Touch which should be open when you run: <code>python spout_NST_receiver_sender.py</code><br>
If working you should see the stylized video feed from the style model you've selected.<br>

<h2>Contributors</h2>

<h2>Acknowledgements</h2>
Fast-style transfer is based on this repo: https://github.com/hwalsuklee/tensorflow-fast-style-transfer <br>
Spout for Python was based on this repo: https://github.com/spiraltechnica/Spout-for-Python <br>
Some set up/dependencies were from Grant Watson's fastyle transfer repository here: https://github.com/ghwatson/faststyle <br>