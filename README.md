# MX object detection : DSでのint8版の認識精度確認用

1. kmcnn_dsp/README.md の手順でdocker環境を用意

2. MX Object detectionの8bit版を作成

```
$ cd kmcnn_dsp/sample/obj_detect_for_mx_20190322
$ quantize.py -f quantize_cfg_8bit.yml
```

3. 1画像を処理 : test_i8c32.sh imagefile

```
root@a1ba0878169a:/work/sample/obj_detect_for_mx_20190322/C# ./test_i8c32.sh ../testdata/O_MC_01-274.jpg 
# detectionOutput                151     2989183 object0 : image_id:0 label: 3 confidence:0.930104 xmin:0.792627 ymin:0.423851 xmax:0.986377 ymax:0.624744
# detectionOutput                151     2989208 object1 : image_id:0 label: 1 confidence:0.903036 xmin:0.419471 ymin:0.332076 xmax:0.498909 ymax:0.711355
# detectionOutput                151     2989211 object2 : image_id:0 label: 3 confidence:0.874395 xmin:0.508274 ymin:0.379880 xmax:0.766942 ymax:0.666581
# detectionOutput                151     2989213 object3 : image_id:0 label: 3 confidence:0.294922 xmin:0.618326 ymin:0.429405 xmax:0.812076 ymax:0.630298
# detectionOutput                151     2989216 object4 : image_id:0 label: 3 confidence:0.204612 xmin:0.487924 ymin:0.414551 xmax:0.681674 ymax:0.615444
# detectionOutput                151     2989218 object5 : image_id:0 label: 3 confidence:0.179709 xmin:0.682009 ymin:0.416361 xmax:0.785134 ymax:0.479394
```

出力文字列を変更したい場合は、 Mynet.hppのdetectionOutput()の'検出結果出力'部分を変更

