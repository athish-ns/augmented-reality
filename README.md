# augmented-reality
Augmented reality card based application with Python, numpy and OpenCV

## Usage

* Place the image of the surface to be tracked inside the `reference` folder.
* On line 36 of `src/ar_main.py` replace `'model.jpg'` with the name of the image you just copied inside the `reference` folder.
* On line 40 of `src/ar_main.py` replace `'fox.obj'` with the name of the model you want to render. To change the size of the rendered model change the scale parameter (number `3`) in line 103 of `src/ar_main.py` by a suitable number. This might require some trial and error.
* Open a terminal session inside the project folder and run `python src/ar_main.py`


### Command line arguments

* `--rectangle`, `-r`: Draws the projection of the reference surface on the video frame as a blue rectangle.
* `--matches`, `-m`: Draws matches between reference surface and video frame.


## Troubleshooting

**If you get the message**:

```
Unable to capture video
```
printed to your terminal, the most likely cause is that your OpenCV installation has been compiled without FFMPEG support. Pre-built OpenCV packages such as the ones downloaded via pip are not compiled with FFMPEG support, which means that you have to build it manually.

**If you get the error**:

```
Traceback (most recent call last):
File "src/ar_main.py", line 174, in
main()
File "src/ar_main.py", line 40, in main
obj = OBJ(os.path.join(dir_name, 'models/fox.obj'), swapyz=True)
File "[...]/augmented-reality/src/objloader_simple.py", line 16, in init
v = v[0], v[2], v[1]
TypeError: 'map' object is not subscriptable
```
