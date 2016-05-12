title: python解析wav获取时长
date: 2015-12-12 14:47:36
tags: python
---

> 通常python解析wav文件可以通过[wave模块](https://docs.python.org/2/library/wave.html)进行操作,但是当wav文件被压缩以后会在使用wave.open函数时会报错,所以需要手工解析wav文件的[头部](http://baike.baidu.com/link?url=fnHBFEj-8Boow8z_Au3SdyR11IUtTvvrYz9Y5AZ_77ED1k1YbOWMZdS7gABBKYE55WZQ2SuRbZcQNkNuX8ktUK)


```python
def getWavDuration():
    path = sys.argv[1]
    f = open(path,'rb')
    #文件大小(B)
    filesize = os.path.getsize(path)
    #声道数
    f.seek(22)
    channel_hex = f.read(2)
    channel = struct.unpack('h',channel_hex)
    #采样率
    f.seek(24)
    samplerate_hex = f.read(4)
    samplerate = struct.unpack('i',samplerate_hex)
    #采样位数(bit)
    f.seek(34)
    sampwidth_hex = f.read(2)
    sampwidth = struct.unpack('h',sampwidth_hex)
    #公式时长=文件大小/(声道数*采样率*采样位数(B))
    duration = filesize / (channel[0] * samplerate[0] * (sampwidth[0]/8))
    return duration
```
