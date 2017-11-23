# emotion-recognition-mlmodel

You can source pre-trained models from a variety of places, or you can train your own. 

A starting place for pre-trained models is [Caffe’s Model Zoo](https://github.com/BVLC/caffe/wiki/Model-Zoo). `.caffemodel` format is supported by `coremltools` for conversion to `.mlmodel` 🎉

To generate the emotion recognition Core ML file, `EmotiClassifier.mlmodel`:

1. Download the [EmotiW_VGG_S.caffemodel](https://drive.google.com/file/d/0BydFau0VP3XSNVYtWnNPMU1TOGM/view)

2. Place `EmotiW_VGG_s.caffemodel` in this repository's directory
   
   This is hosted by the original authors of the *Emotion Classification CNN*, Gil Levi and Tal Hassner. More information about the model development and corresponding paper can be found [here](https://gist.github.com/GilLevi/54aee1b8b0397721aa4b)
   
   Paper and model info is aggregated in the [Caffe Model Zoo](https://github.com/BVLC/caffe/wiki/Model-Zoo)
 
3. Check that this repository contains all of the files needed
  `convert_to_mlmodel.ipynb`: Jupyter notebook with Python commands for converting **caffe model** to **ML Model**
  `EmotiW_VGG_s.caffemodel` file: original model representation
  `deploy.prototxt` file: metadata about model
  `labels.txt` file: classifications model out corresponds to (e.g. "Happy", "Sad", "Angry")

4. Check that dependencies are installed correctly. We're required to use Python < 3.0, and it is recommended to use virtualenv to run it.

`pip install --upgrade pip
pip install –U virtualenv
cd ~
virtualenv --python=/usr/bin/python2.7 coreml
source coreml/bin/activate
pip install -U coremltools
pip install -U jupyter`


5. `jupyter notebook`

   This should launch the Jupyter Notebook in your browser http://localhost:8888/tree, listing your files  

6. Open `convert_to_mlmodel.ipynb` in Jupyter Notebook

7. Execute each cell one by one, `Ctrl` + `Enter` (denoted with a border around it)

*Alternatively, you could just click **Cell -> Run All**. However, I think it is useful to step through each line to understand what is involved in the conversion.*
