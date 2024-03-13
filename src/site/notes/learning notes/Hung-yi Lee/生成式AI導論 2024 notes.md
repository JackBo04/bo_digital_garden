---
{"dg-publish":true,"permalink":"/learning notes/Hung-yi Lee/生成式AI導論 2024 notes/"}
---

by Huangbo Zou

## 0-1 课程说明&生成式ai是什么
### 概念：
1. 人工智慧(Artificial Intelligence, AI)（目标）：讓機器展現「智慧」
2. 生成式人工智慧 (Generative AI)： 機器產生複雜有結構的物件
3. 機器學習 ≈ 機器自動從資料找一個函式 (Machine Learning)
4. 深度學習(Deep Learning) 是一種機器學習技術，一般使用<font color="#0070c0">類神經網路 (Neural Network)</font>(Transformer :類神經網路的一種)
5. 
![Pasted image 20240312182453.png](/img/user/pasted_image/Pasted%20image%2020240312182453.png)
## 2 今日的生成式人工智慧厲害在哪裡？

### 总结现状：
从工具迈向工具人，不再是只能执行某一类特定任务的工具，而是能调用多种工具模块执行完善的prompt的要求

不要問 ChatGPT 能為你做什麼 要問你想要 ChatGPT 幫你做什麼 (你認為ChatGPT 是「工具」，只有某些固定功能) (只要你下對指示，ChatGPT就能幫助你)

### 現在人工智慧已經從「工具」 進化成「工具人」，那我還能做甚麼？
#### 思路一：我改不了模型，那我改變我自己
![Pasted image 20240312183048.png](/img/user/pasted_image/Pasted%20image%2020240312183048.png)Prompt Engineering: 人類與人工智慧溝通的藝術
#### 思路二：我要訓練自己的模型
调整开源模型的函数
![Pasted image 20240312183213.png](/img/user/pasted_image/Pasted%20image%2020240312183213.png)
## 3 訓練不了人工智慧？ 那我訓練自己(上)

### Prompt Engineering
keypoints：
- 給語言模型的 prompt 不需要特定格式
- 按照今天語言模型能力，你把需要的任務描述清楚即可

### 有那些在不訓練模型的情況下強化語言模型的方法？
![Pasted image 20240312183550.png](/img/user/pasted_image/Pasted%20image%2020240312183550.png)

#### 1.神奇咒語!

> 免責聲明：神奇咒語並不一定對所有模型、所有任務都適用

1. Chain of Thought (CoT):一句简单的"think about it step by step",居然能提升模型某些任务的表现(gpt4——看图)
2. 請模型解釋一下自己的答案
3. 對模型情緒勒索：任务+这对我的事业非常重要...之类
4. ...还有很多
5. 用AI來找神奇咒語：用增強式學習 (Reinforcement Learning, RL)
![Pasted image 20240312184107.png](/img/user/pasted_image/Pasted%20image%2020240312184107.png)
![Pasted image 20240312184131.png](/img/user/pasted_image/Pasted%20image%2020240312184131.png)
现在对于完备的大模型，可以直接提问:"我使用什么prompt可以让你回答地更好"
![Pasted image 20240312184340.png](/img/user/pasted_image/Pasted%20image%2020240312184340.png)
#### 2. 提供額外資訊
方法：
1. 把前提講清楚
![Pasted image 20240312184421.png](/img/user/pasted_image/Pasted%20image%2020240312184421.png)
2. 提供生成式AI不清楚的資訊(上传附件)
3. <font color="#0070c0">提供範例(In-context learning)</font>：其实模型不会真正学习范例，目前最强的大模型只会在本次回答时受到错误范例的影响，模型本身不会被训练。 ![Pasted image 20240312184714.png](/img/user/pasted_image/Pasted%20image%2020240312184714.png)
#### 3. 把任務分多步驟來解
任务可以分为三个步骤来提高准确率（三个步骤打组合拳）
1. 複雜的任務拆解成多個步驟
2. 模型檢查自己的答案
3. 同一個問題每次答案都不同
![Pasted image 20240312184905.png](/img/user/pasted_image/Pasted%20image%2020240312184905.png)
拆解任务:在解数学问题拆解步骤时，模型先列出的式子会被添加到input中，这样依据完善的input来做概率接龙就更有可能达到正确的结果。
![Pasted image 20240312185132.png](/img/user/pasted_image/Pasted%20image%2020240312185132.png)
检查错误：語言模型可以自我反省
![Pasted image 20240312185504.png](/img/user/pasted_image/Pasted%20image%2020240312185504.png)
每次答案都不同：重复输入，出现概率最高的答案更有可能是正确答案

Tree of Thoughts (ToT)：(组合拳)
![Pasted image 20240312185614.png](/img/user/pasted_image/Pasted%20image%2020240312185614.png)

还剩下方法四：让大模型使用工具
方法五：大模型之间的协作

## 4 訓練不了人工智慧？ 那我訓練自己(中)

#### 4.使用工具

##### Retrieval Augmented Generation (RAG)
待填坑
![Pasted image 20240312190125.png](/img/user/pasted_image/Pasted%20image%2020240312190125.png)

##### Program of Thought (PoT)
人工智能会写程序来完成自己不擅长的任务（例如数学计算，仅凭概率来文字接龙是无法给出准确答案的）
![Pasted image 20240312190350.png](/img/user/pasted_image/Pasted%20image%2020240312190350.png)

##### 使用工具 – 文字生圖 AI (DALL-E)
![Pasted image 20240312190440.png](/img/user/pasted_image/Pasted%20image%2020240312190440.png)

##### 語言模型是怎麼使用工具的呢？
其實使用工具都是文字接龍
![Pasted image 20240312190523.png](/img/user/pasted_image/Pasted%20image%2020240312190523.png)

#### 5. 語言模型彼此合作
![Pasted image 20240312190613.png](/img/user/pasted_image/Pasted%20image%2020240312190613.png)
核心思想：
1. 讓合適的模型做合適的事情：会出现一个模型专门判断这个任务该给哪个模型完成，再调用"工具模型"完成任务,决策模型会综合考虑不同模型的能力和成本。
2. 讓模型彼此討論：
	1. 模型A的输入和输出会打包给模型B进行评判，将建议反馈给模型A进行更好的生成。
	2. Multi-agent Debate，模型A和B会关于问题中A的解决步骤（假设交给A执行）进行争论，在对解决方案找问题的否定中更可能得出正确的答案。实验证明Multi-agent Debate对解决方案的否定次数明显高于模型的Self-Reflection(自我反省)，更有可能得出正确的答案。
	![Pasted image 20240312191136.png](/img/user/pasted_image/Pasted%20image%2020240312191136.png)
		1. 多模型怎麼討論：不同任務最合適的討論方式是不一樣的
		2. 討論要怎麼停下來？![Pasted image 20240312191841.png](/img/user/pasted_image/Pasted%20image%2020240312191841.png)
		3. 引入不同的腳色
			![Pasted image 20240312192010.png](/img/user/pasted_image/Pasted%20image%2020240312192010.png)
			Dynamic LLM Agent Network：CEO角色：根據上述對話，給每個人的貢獻度打分數，分數太低的之後就不參與工作
			![Pasted image 20240312192155.png](/img/user/pasted_image/Pasted%20image%2020240312192155.png)
		
	
