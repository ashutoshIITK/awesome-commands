# Useful tips and tricks for Bash, Python, etc. 

## String Operations

#### Find the exact occurrence of strings in a folder

```bash
for string in string1 string2 string3 string4; do grep -rohw $string . | wc -l; done
```

#### Replace stringA with stringB (inplace) in all the files inside a folder
```bash
find ./ -type f -exec sed -i 's/stringA/stringB/g' {} \;

```

#### For Loop (Range) in Bash
```bash
for i in {0..N..STEP}; do echo "$i"; done
```

## Image processing

#### Reduce size of the images
```bash
mogrify -quality 50% *
```
#### Load exact image channels OpenCV
- By default, OpenCV imread loads three channels (W, H, C). To override this behaviour, use the following flag while using cv2.imread
```python
frame = cv2.imread("/path/of/image", CV2.IMREAD_UNCHANGED)
```
## File Management

##### Move/Copy n files from a folder


## Remote Management

##### Killing frozen VNC server

Warning: $HOSTNAME:6 is taken because of /tmp/.X6-lock
Remove this file if there is no X server $HOSTNAME:6

```bash
rm -f /tmp/.X6-lock
rm -f /tmp/.X11-unix/X6
```

In the above command, replace X6 with the display number on which you are running VNC server. For example, if you started VNC server on screen 1 as vncserver :1 -geometry 1920x1200, then please use X1. Likewise, if you were running VNC server on screen 2, then use X2, and so on.

##### Hide PyGame Window

If you are running a script externally using bash loop and if it is required to process without requiring the GUI (PyGame) window to show up, just put the "SDL_VIDEODRIVER" to environment variable as "dummy".

```python
import os
os.environ["SDL_VIDEODRIVER"] = "dummy"
```

## Web Development

## Application Software
