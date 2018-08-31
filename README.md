# RNN撰写诗词 

### 长短时记忆网络（Long short term memory，LSTM）是一种循环神经网络（Recurrent neural network，RNN）。以诗词《全宋词》为训练数据，基于RNN用LSTM语言模型训练了一个人工智能写词机。

## 1 &nbsp;算法
####  LSTM语言模型算法：[model.py](https://github.com/fxfviolet/RNN_for_writing_poem/blob/master/model.py)。通过 tf.nn.rnn_cell.BasicLSTMCell定义单个基本的LSTM单元，用tf.nn.rnn_cell.MultiRNNCell实现深层循环神经网络中每一个时刻的前向传播过程，构造完多层LSTM以后，通过tf.nn.dynamic_rnn创建递归神经网络。最后用交叉熵计算loss损失进行优化。
####  文本处理算法：[utils.py](https://github.com/fxfviolet/RNN_for_writing_poem/blob/master/utils.py)。 读取文件“QuanSongCi.txt”作为训练数据，将文件中的句子转换为词汇列表（英文文本转换为单词列表，中文文本转换为字列表）。
####  诗词训练：[train.py](https://github.com/fxfviolet/RNN_for_writing_poem/blob/master/train.py)。对处理后的数据运用上述算法进行参数优化，优化得到的权重参数存入model.ckpt中。
####  诗词撰写：[sample.py](https://github.com/fxfviolet/RNN_for_writing_poem/blob/master/sample.py)。加载预训练模型，得到权重参数，用LSTM模型算法撰写诗词。

## 2 &nbsp;结果
#### 得到的部分测试结果如下：
江神子      
水调歌头（寿赵）     
一日一年，一笑一年，一笑一年，一笑一年，一笑一年，一笑一年，一笑一年，一笑一年。     
蝶恋花       
一点春风，一点春风，一点春风，一点春风，一点春风，一点春风，一点春风，一点春风。     




 

 
