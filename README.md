To run a new video... go to terminal and write the command 

```ffmpeg -f concat -safe 0 -i input.txt -framerate 30 -c:v libx264 -pix_fmt yuv420p outputLG.mp4```

To get a 30fps video names outputLG.mp4

If we want a 15 fps video

```ffmpeg -f concat -safe 0 -i input.txt -framerate 15 -c:v libx264 -pix_fmt yuv420p output.mp4```



If we re-export new images, we need to re index the files in sequential order with


```ls -v *.jpeg > filelist.txt```

To add the new order to fileList.txt

Then rewrite input.txt from fileList.txt like so

```while read line; do
    echo "file '$PWD/$line'"
done < filelist.txt > input.txt```
