## Starting the enviorment:
```
git clone --recursive --depth=1 https://github.com/dusty-nv/jetson-inference
cd jetson-inference
docker/run.sh
```

## Live Obj Detection

# MIPI CSI camera
```
python/examples/detectnet.py csi://0
```

# IP camera
```
python/examples/detectnet.py rtsp://10.10.10.10:10/stander/livestream/0/0
```

# V4L2 camera
```
python/examples/detectnet.py /dev/video0
```

# Save to video file
```
python/examples/detectnet.py /dev/video0 output.mp4
```

## People Tracking:

# Download test video (Optional iff video is downloaded)
```
wget https://nvidia.box.com/shared/static/veuuimq6pwvd62p9fresqhrrmfqz0e2f.mp4 -O pedestrians.mp4
```

# Python
```
python/examples/detectnet.py --model=peoplenet --tracking pedestrians.mp4 pedestrians_tracking.mp4
```

# With Snap
```
python/examples/detectnet-snap.py --model=peoplenet  /dev/video0
```
