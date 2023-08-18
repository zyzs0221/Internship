训练过程：

![image-20230817162556110](C:\Users\Sun\AppData\Roaming\Typora\typora-user-images\image-20230817162556110.png)

测试过程：

我们组首先使用原代码的测试部分进行测试，测试结果如下：

![image-20230817162726382](C:\Users\Sun\AppData\Roaming\Typora\typora-user-images\image-20230817162726382.png)

之后我们修改图片的输入源，将视频帧进行输入，让模型识别视频中的物体

核心代码：

```python
    #将图片的输入源换成视频
    video_path = "test_1.mp4"  # 替换为你的输入视频路径
    cap = cv2.VideoCapture(video_path)

    frame_width = int(cap.get(3))
    frame_height = int(cap.get(4))
    out = cv2.VideoWriter('output_video.mp4', cv2.VideoWriter_fourcc(*'XVID'), 30, (frame_width, frame_height))


    while True:
        ret, frame = cap.read()
        if not ret:
            break
        # cv2.imshow('pic',frame)
        # cv2.waitKey(0)
        img=frame
```

![image-20230817164857246](C:\Users\Sun\AppData\Roaming\Typora\typora-user-images\image-20230817164857246.png)

效果展示：

见附件



