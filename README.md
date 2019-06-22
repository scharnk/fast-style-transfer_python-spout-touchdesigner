# fast-style-transfer_python-spout-touchdesigner
This repository is a tensorflow implementation of fast-style transfer in python to be sent into touchdesigner
To talk to both programs Spout is required.

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
  <li>Tensorflow 1.0.0
    <ul><code>Python -m pip install tensorflow_gpu==1.0.0</code></ul>
    <ul>(may have to upgrade pip first before this will run)
  </li>
  <li>Opencv 3.1.0
  <ul><code>Pip install opencv-python==3.1.0</code></ul>
  </li>
  <li>Restart computer</li>
</ul>

<br>

<h4>To run from terminal set directory to project location & set parameters to stylize webcam: </h4>
<code>cd C:\Users\_______\Documents\faststyle35</code><br>
<code>python stylize_webcam.py --model_path ./models/starry_final.ckpt --resolution 1920 1080</code><br>
*lowering resolution can increase refresh rate of video<br>
<h2>Contributors</h2>

<h2>Acknowledgements</h2>
Fast-style transfer is based on this repo: https://github.com/hwalsuklee/tensorflow-fast-style-transfer
Spout for Python was based on this repo: https://github.com/spiraltechnica/Spout-for-Python
Python dependencies were taken from Grant Watson's fastyle transfer repository here: https://github.com/ghwatson/faststyle
