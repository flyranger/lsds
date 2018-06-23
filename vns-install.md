ubuntu gvns install
===========================

## 1. libboost-1.55.0 安装

### 1.1 依赖包安装
```
sudo apt-get update
sudo apt-get install build-essential g++ python-dev autotools-dev libicu-dev build-essential libbz2-dev libboost-all-dev
```

### 1.2 下载boost-1.55.0 并解压
```
wget -O boost_1_55_0.tar.gz http://sourceforge.net/projects/boost/files/boost/1.55.0/boost_1_55_0.tar.gz/download
tar xzvf boost_1_55_0.tar.gz
```

### 1.3 boost-1.55.0 安装
```
./bootstrap.sh --prefix=/usr/local
./b2 install --prefix=/usr/local
sudo ldconfig -v
```

## 2. vns节点启动并开启挖矿

### 2.1 创建VNS挖矿奖励地址
```
./gvns account new    //接下来输入两次密码
Passphrase:
Repeat passphrase:
Address: {xxxxx}     //创建的挖矿地址
```

### 2.2 启动节点并开启挖矿
```
nohup ./gvns --mine --vnsbase xxxxx &    //vnsbase后面的参数是 2.1 步骤中创建的VNS挖矿地址
```

## **WARNING** 务必让矿机与网络时间同步，以免不能正常开启挖矿。

gvns md5sum: 21d877063289a280335bf665860d5bae
