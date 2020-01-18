# Neural-Image-Style-Transfer

## neural-style

An implementation of neural style in TensorFlow.

This implementation is a lot simpler than a lot of the other ones out there, thanks to TensorFlow's really nice API and automatic differentiation.

TensorFlow doesn't support L-BFGS (which is what the original authors used), so we use Adam. This may require a little bit more hyperparameter tuning to get nice results.


## Running
```python neural_style.py --content <content file> --styles <style file> --output <output file> ```

Run python neural_style.py --help to see a list of all options.

If you are running this project on Floydhub you can use the following syntax (this pulls in the pre-trained VGG network automatically):

```floyd run --gpu --env tensorflow-1.3 --data floydhub/datasets/imagenet-vgg-verydeep-19/3:vgg "python neural_style.py --network /vgg/imagenet-vgg-verydeep-19.mat --content <content file> --styles <style file> --output <output file>" ```

Use ```--checkpoint-output``` and ```--checkpoint-iterations``` to save checkpoint images.

Use ```--iterations``` to change the number of iterations (default 1000). For a 512×512 pixel content file, 1000 iterations take 60 seconds on a GTX 1080 Ti, 90 seconds on a Maxwell Titan X, or 60 minutes on an Intel Core i7-5930K. Using a GPU is highly recommended due to the huge speedup.


## Requirements
Data Files
[Pre-trained VGG network](http://www.vlfeat.org/matconvnet/models/imagenet-vgg-verydeep-19.mat) (MD5 106118b7cf60435e6d8e04f6a6dc3657) - put it in the top level of this repository, or specify its location using the --network option.

## Dependencies
You can install Python dependencies using pip install -r requirements.txt, and it should just work. If you want to install the packages manually, here's a list:

- TensorFlow
- NumPy
- SciPy
- Pillow

## INPUT 
![INPUT1](https://https://github.com/madamalarevanth/Neural-Image-Style-Transfer/blob/master/examples/nar.jpg)




## Citation
If you use this implementation in your work, please cite the following:
```
@misc{athalye2015neuralstyle,
  author = {Anish Athalye},
  title = {Neural Style},
  year = {2015},
  howpublished = {\url{https://github.com/anishathalye/neural-style}},
  note = {commit xxxxxxx}
} 
```
## License
Copyright (c) 2015-2019 Anish Athalye. Released under GPLv3. See LICENSE.txt for details.
