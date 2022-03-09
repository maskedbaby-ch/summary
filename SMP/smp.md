#SMP

SMP 三个阶段

* 配对密钥特征交换
    - 鉴权信息
        - Just work 密钥默认 000000
        - Numeric comparison 两个设备协商一个 6 位数据
        - passkey entry 输入数据
        - out of band 带外入网
    - IO 能力
    - legacy / secure

![image](./smp.png)

    
* key 产生
    * 如果是 legacy，产生 STK，短期密钥
    * 如果是 secure，产生 LTK，长期密钥

* 密钥分发 
    * 分发其他一些密钥，比如 IRK，CSRK，SK 等

IRK：ble 设备地址有两类，public address 和 random address，public address 需要申请，全球唯一，random address 又分为 static address 和 private address. private address 又分为可解析的和不可解析的，private address 会定时更新，可解析的地址，private resovlable address 是由随机数和 IRK 密钥计算生成的，所以只有拥有 IRK 的设备才能解析出地址。防止其他设备攻击。 

CSRK：不加密，但发送带签名的消息让，别的设备识别








