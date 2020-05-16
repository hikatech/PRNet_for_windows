# PRNet for Python 3.x for Windows

## ライセンス

* 元コードのライセンスはMIT Licenseです。
* 本リポジトリで追加しているコードもMIT Licenseとします。
* **サンプルモデルは非営利目的の場合のみ使用可**のようですが、詳しくは[ここ](https://github.com/YadiraF/PRNet/issues/28)を参照してください。

## 準備とテスト実行

### 想定する環境

* Windows 10
* CUDA 10.0 (with cuDNN)
* Python 3.7.5-amd64 (numpy, skimage, scipy
  * TensorFlow -gpu == 1.15.2
  * dlib
  * opencv2 (for showing results)

GPUはほとんど必須だと思ったほうがいいです。テストはQuadroT2000搭載のラップトップPCで行いました。

### 使い方

1. リポジトリをClone

  ```bash
  git clone https://github.com/hikatech/PRNet.git
  cd PRNet
  ```

2. requirementsをインストール

  ```bash
  pip3 install -r requirements.txt
  ```

3. Dlibをインストール：[参考: Python用にdlibをインストール（Windows）](https://qiita.com/Kurobani/items/fd84fd941f527c46ab98#2-cmake%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB)

4. 学習済みモデルをYao Feng氏らが用意してくれている（感謝）。[BaiduDrive](https://pan.baidu.com/s/10vuV7m00OHLcsihaC-Adsw)または[GoogleDrive](https://drive.google.com/file/d/1UoE-XuW1SDLUjZmJPkIZ1MLxvQFgmTFH/view?usp=sharing)からダウンロードし、`Data/net-data`に配置する

5. テストコードを実行する場合(test AFLW2000 images)

   `python run_basics.py #Can run only with python and tensorflow`

6. 用意した画像群を処理させる場合（dlib必要）

   `python demo.py -i <inputDir> -o <outputDir> --isDlib True  `

   詳しくは `python demo.py --help` を参照のこと。

7. Texture Editing Appsを起動する場合:

   `python demo_texture.py -i image_path_1 -r image_path_2 -o output_path   `

   詳しくは `python demo_texture.py --help` を参照のこと。


## ----以下、引用

## License

Code: under MIT license.

Trained model file: please see [issue 28](https://github.com/YadiraF/PRNet/issues/28), thank [Kyle McDonald](https://github.com/kylemcdonald) for his answer.



## Citation

If you use this code, please consider citing:

```
@inProceedings{feng2018prn,
  title     = {Joint 3D Face Reconstruction and Dense Alignment with Position Map Regression Network},
  author    = {Yao Feng and Fan Wu and Xiaohu Shao and Yanfeng Wang and Xi Zhou},
  booktitle = {ECCV},
  year      = {2018}
}
```



## Contacts

Please contact _fengyao@sjtu.edu.cn_  or open an issue for any questions or suggestions.

Thanks! (●'◡'●)



## Acknowledgements

- Thanks [BFM team](https://faces.dmi.unibas.ch/bfm/), [Xiangyu Zhu](http://www.cbsr.ia.ac.cn/users/xiangyuzhu/projects/3DDFA/main.htm), and [Anil Bas](https://github.com/anilbas/3DMMasSTN) for sharing 3D data.
- Thanks Patrik Huber for sharing his work  [eos](https://github.com/patrikhuber/eos), which helps me a lot in studying 3D Face Reconstruction.
- Thanks the authors of  [3DMMasSTN](https://github.com/anilbas/3DMMasSTN), [DenseReg](https://github.com/ralpguler/DenseReg), [3dmm_cnn](https://github.com/anhttran/3dmm_cnn), [vrn](https://github.com/AaronJackson/vrn), [pix2vertex](https://github.com/matansel/pix2vertex), [face-alignment](https://github.com/1adrianb/face-alignment) for making their excellent works publicly available. 
