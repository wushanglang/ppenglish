### 英语外刊阅读

##### 在线访问  
- 国内：[ppenglish.tech](https://www.ppenglish.tech/) 
- 国际：[https://bubble-henna.vercel.app](https://ppenglish.vercel.app/)

<br>

##### 演示          
![image](https://github.com/user-attachments/assets/d0376f4d-c34d-4153-8bbc-72cea6491585)

![image](https://github.com/user-attachments/assets/1cd94160-a87e-4d36-aa30-cd09a2697109)

![image](https://github.com/user-attachments/assets/b671e4c0-6826-4882-b216-61206d08326b)

<br>

##### 特点

- 千问大模型AI翻译
- 主流外刊文章，适配四六级、考研等英语学习者需求
- 用户自定义布局
  - 字体样式 fontFamily
  - 字体大小 fontSize
  - 行间距 lineHeight   
  - 单双列布局
  - 主题
- markdown笔记（TODO） 
 
<br>

##### 数据来源

文章来源于主流期刊杂志， 翻译由qwen-plus提供：   
```python
# 阿里千问api_key
dashscope.api_key = ""

def AITranslate(content):
    messages = [
        {
            "role": "system",
            "content": "You will be provided with statements, and your task is to translate them to standard Chinese.",
        },
        {
            "role": "user",
            "content": content,
        },
    ]
    response = Generation.call(
        model="qwen-plus",
        messages=messages,
        seed=random.randint(1, 10000),
        result_format="message",
    )
    if response.status_code == HTTPStatus.OK: 
        return response.output.choices[0].message.content
    else: 
        return ""
```


<br>

##### 查词功能

网站不提供查词功能，可安装 [欧路翻译 - 网页划词翻译工具 (google.com)](https://chromewebstore.google.com/detail/欧路翻译-网页划词翻译工具/djbfechcnkppbknmlhfcaoifgnicolin)等插件实现。

<br>

##### 反馈           
网站开源且长期更新，希望得到你的帮助。<br>
如果你有好的想法或者文章数据源，请到  [github](https://github.com/wushanglang/ppenglish)上提交issue。  



