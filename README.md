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
## Image processing

#### Reduce size of the images
```bash
mogrify -quality 50% *
```
#### Load exact image channels OpenCV
- By default, OpenCV imread loads three channels (W, H, C). To override this behaviour, use the following flag while using cv2.imread
```bash
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

## Web Development

## Application Software
