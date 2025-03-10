<h1 align="center">孙思邈中文医疗大模型</h1>
<p align="center">

<p align="center">
<a href="https://github.com/thomas-yanxin/Sunsimiao"><img src="https://img.shields.io/badge/GitHub-24292e" alt="github"></a>
<a href="https://huggingface.co/thomas-yanxin/Sunsimiao-01M-lora"><img src="https://img.shields.io/badge/HuggingFace-yellow" alt="HuggingFace"></a>
<a href="https://modelscope.cn/organization/X-D-Lab"><img src="https://img.shields.io/badge/ModelScope-blueviolet" alt="modelscope"></a>
<a href="https://openi.pcl.ac.cn/Learning-Develop-Union/Sunsimiao"><img src="https://img.shields.io/badge/-OpenI-337AFF" alt="OpenI"></a>
<a href="https://wisemodel.cn/models/X-D%20Lab/Sunsimiao"><img src="https://img.shields.io/badge/wisemodel-561253" alt="wisemodel"></a>
</p> 

<div align="center">

[![GitHub LICENSE](https://img.shields.io/github/license/X-D-Lab/Sunsimiao)](https://github.com/X-D-Lab/Sunsimiao/stargazers)
[![GitHub Stars](https://img.shields.io/github/stars/X-D-Lab/Sunsimiao)](https://github.com/X-D-Lab/Sunsimiao/blob/main/LICENSE)
[![GitHub Forks](https://img.shields.io/github/forks/X-D-Lab/Sunsimiao)](https://github.com/X-D-Lab/Sunsimiao/fork)
[![GitHub Contributors](https://img.shields.io/github/contributors/X-D-Lab/Sunsimiao)](https://github.com/X-D-Lab/Sunsimiao/graphs/contributors)  
**[中文](README_CN.md) | [English](README_EN.md)**
</div>
<div align=center><img width = '400' height ='400' src ="./image/sunsimiao.png"/></div>  

### 模型介绍

**孙思邈**, 唐代医药学家、道士, 被后人尊称为"药王". 其十分重视民间的医疗经验, 不断积累走访, 及时记录下来, 写下著作《千金要方》. 唐朝建立后, 孙思邈接受朝廷的邀请, 与政府合作开展医学活动, 完成了世界上第一部国家药典《唐新本草》.  

**孙思邈中文医疗大模型**(简称: Sunsimiao)希望能够遵循孙思邈的生平轨迹, 重视民间医疗经验, 不断累积中文医疗数据, 并将数据附加给模型, 致力于提供**安全、可靠、普惠**的中文医疗大模型.  

此外, 本团队同时关注人们的心理健康, 致力于为用户提供**隐私、温暖、舒适、及时、方便**的心理服务的[MindChat(漫谈)心理大模型](https://github.com/X-D-Lab/MindChat), 欢迎关注, 敬请批评指证!

### 模型列表

| 模型名称 | lora权重 | 合并后的权重 |
| :----: | :----: | :----: |
| Sunsimiao-01M | [modelscope](https://modelscope.cn/models/thomas/Sunsimiao_lora/summary) / [huggingface](https://huggingface.co/thomas-yanxin/Sunsimiao-0.1M-lora) | [modelscope](https://modelscope.cn/models/AI-ModelScope/Sunsimiao/summary) / huggingface |
| Sunsimiao-01M-Chat | [modelscope](https://modelscope.cn/models/thomas/Sunsimiao-01M-Chat-lora/summary) / huggingface | [modelscope](https://modelscope.cn/models/thomas/Sunsimiao-01M-Chat/summary) / huggingface |
| Sunsimiao-01M-6B* | modelscope / huggingface | [modelscope](https://modelscope.cn/models/thomas/Sunsimiao-6B/summary) / huggingface |
| Sunsimiao-InternLM-01M* | modelscope / huggingface | [modelscope](https://modelscope.cn/models/thomas/Sunsimiao-InternLM-01M/summary) / huggingface |

### 使用方法

```Python
from modelscope.pipelines import pipeline
from modelscope.utils.constant import Tasks

pipe = pipeline(task=Tasks.text_generation, model='AI-ModelScope/Sunsimiao', model_revision='v1.0.0')

query = '小孩发烧了怎么办？'

prompt="Below is an instruction that describes a task. Write a response that appropriately completes the request."
prompt+="### Instruction:\n{}\n\n### Response:\n".format(query)

result = pipe(prompt)
print(result)
```

```
{'text': 'Below is an instruction that describes a task. Write a response that appropriately completes the request.### Instruction:\n小孩发烧了怎么办？\n\n### Response:\n\n如果您的孩子发烧了，您可以参考以下建议：\n\n1. 帮助孩子退热：\n\n将冷水倒入一个杯子，放在孩子的腋下(或额头)，每5分钟转一次。\n\n将冰毛巾擦在孩子的胸部、颈部和后背。\n\n将退烧药放在孩子额头或颈部。\n\n2. 检查孩子的症状：\n\n是否咳嗽、鼻塞或流鼻涕？\n\n3. 根据症状：\n\n如果孩子咳嗽，可以给孩子喝些水或温水，并给孩子喝一些蜂蜜;\n\n如果孩子鼻塞，可以给孩子吸入一些蒸汽;\n\n如果孩子发烧，可以给孩子喂些温水，并让孩子休息;\n\n如果孩子呼吸急促或呼吸困难，应立即就医。\n\n4. 如果孩子有其他不适：\n\n如果孩子没有食欲或呕吐，可以给孩子吃些软餐;\n\n如果孩子感到疲倦，可以让孩子休息;\n\n如果孩子的眼睛出现红色或分泌物，应立即就医。\n\n5. 注意孩子的个人卫生：\n\n让孩子勤喝水，勤洗手，保持室内通风;\n\n避免孩子与别的孩子进行密切接触，以免传染。\n\n祝您的孩子早日康复！'}
```  
**更多使用方法见[scripts](./scripts/)**

### 部分测试

| Human | Sunsimiao_01M_Chat| Sunsimiao_05M_v2 | Sunsimiao-InternLM-01M |
| :----: | ---- | ---- | ---- |
| 小孩发烧怎么办? | 如果您的孩子发烧, 您可以采取以下措施:<br/>1. 给孩子多喝水. 发烧会导致身体脱水, 所以要让孩子多喝水以补充水分和电解质.<br/>2. 给孩子服用退烧药. 如果孩子的体温超过38°C, 建议使用退烧药物来缓解症状. 但是请注意, 不要随意给孩子使用药物, 最好咨询医生的意见.<br/>3. 给孩子进行物理降温. 可以用温水擦浴、冷敷等方法帮助孩子降低体温.<br/>4. 保持室内通风. 在孩子发烧期间, 应该保持室内空气流通, 避免空气不流通导致细菌滋生.<br/>5. 观察孩子的病情变化. 如果孩子的体温持续升高或者出现其他不适症状, 应及时就医. | 如果孩子发烧, 可以采取以下措施:<br/>1. 让孩子多喝水. 水是身体的重要组成部分, 喝足够的水有助于保持体内水分平衡和促进新陈代谢.<br/>2. 用温湿毛巾敷在孩子的额头上, 帮助降低体温.<br/>3. 如果孩子有咳嗽、流鼻涕等症状, 可以用盐开水给孩子漱口或用生理盐水滴鼻子.<br/>4. 在家里准备一些退烧药, 如布洛芬等, 以备不时之需. 但需要注意的是, 药物必须按照医生的建议使用, 不能随意增加剂量或者延长用药时间. 同时, 不要让宝宝自行服用药物, 以免出现不良反应. | 如果小孩发烧，建议先给小孩测量体温，如果体温超过38.5℃，可以使用退烧药，如布洛芬或对乙酰氨基酚等。同时，可以给孩子多喝水，保持室内空气流通，并注意观察孩子的精神状态和食欲。如果体温持续不退或者出现其他症状，建议及时就医。另外，注意保持小孩的卫生和休息，避免接触感染源。如果小孩有其他疾病或过敏史，请遵医嘱用药。请注意，退烧药不能代替医生的诊断和治疗。如有疑问，请咨询医生。 |
| 一岁宝宝发烧能吃啥药? | 对于一岁的宝宝, 建议不要随意使用药物治疗. 如果宝宝只是轻微的发热, 可以多喝水、注意休息和观察病情变化. 如果宝宝体温超过38°C, 可以给宝宝服用退烧药, 如对乙酰氨基酚等. 但是, 一定要按照药品说明书上的用法用量进行用药, 避免过量或不足. 同时, 最好咨询医生的意见, 以确保安全有效地控制宝宝的发热症状. | 对于一岁的宝宝, 建议不要随意使用药物治疗. 如果宝宝只是轻微的发热, 可以多喝水、注意休息和观察病情变化. 如果宝宝体温超过38°C, 可以给宝宝服用退烧药, 如对乙酰氨基酚等. 但是, 一定要按照药品说明书上的用法用量进行用药, 避免过量或不足. 同时, 最好咨询医生的意见, 以确保安全有效地控制宝宝的发热症状. | 一岁宝宝发烧时，最好不要给药，因为宝宝的身体机能还比较弱，药物可能会对宝宝的身体产生不良影响。建议您采取以下措施来缓解宝宝的发烧症状：<br/>1. 给宝宝多喝水，保持充足的水分摄入。<br/>2. 给宝宝穿宽松、透气的衣服，保持室内空气流通。<br/>3. 给宝宝用温水擦拭身体，缓解宝宝的身体不适。<br/>4. 如果宝宝发烧超过38.5℃，可以考虑使用退烧药，但需要在医生的指导下使用。<br/>5. 如果宝宝有其他不适症状，如呕吐、腹泻等，需要及时就医。<br/><br/>请注意，以上建议仅供参考，如有疑问，请咨询专业医生。 |
| 医生, 您好白带增多泛黄怎么回事? | 你好, 根据你的描述, 可能是阴道炎、宫颈糜烂等妇科疾病引起的. 建议你及时就医, 进行相关检查和治疗. 同时注意个人卫生, 保持外阴清洁干燥, 避免穿紧身裤或合成材料的内衣, 以免加重症状. | 你好, 根据你的描述, 可能是阴道炎、宫颈糜烂等妇科疾病引起的. 建议你及时就医, 进行相关检查和治疗. 同时注意个人卫生, 保持外阴清洁干燥, 避免穿紧身裤或合成材料的内衣, 以免加重症状. | 您好，白带增多泛黄可能是由于多种原因引起的，例如阴道感染、荷尔蒙水平变化、药物使用、性行为等。建议您尽快就医，进行相关检查和诊断，以确定病因并采取相应的治疗措施。同时，注意个人卫生，保持阴道清洁干燥，避免使用刺激性药物和化妆品，避免过度清洁和使用不合适的卫生巾和卫生棉条等。如果您有性行为，建议您在性行为前使用安全套，以减少感染的风险。请务必咨询医生以获取更详细的建议和指导。祝您健康！ |
| 心肌梗塞能治疗吗? | 心肌梗塞是一种严重的疾病, 需要及时的治疗. 目前, 心肌梗塞的治疗主要包括药物治疗和手术治疗两种方式. 药物治疗主要是通过口服或静脉注射一些抗凝血药、扩张血管药等来改善心脏供血情况, 缓解症状. 手术治疗则是通过冠状动脉旁路移植术、支架植入术等方式来恢复心脏的正常功能. 此外, 患者还需要注意饮食健康, 保持良好的心态和生活习惯, 以促进康复. | 心肌梗塞是一种严重的疾病, 需要及时的治疗. 目前, 对于急性心肌梗塞患者来说, 最主要的是尽早开通血管, 恢复心脏供血功能. 在药物治疗的基础上, 可以采用介入手术、冠状动脉搭桥术等方法进行治疗. 同时, 还需要注意患者的饮食和生活习惯, 避免过度劳累和情绪波动等情况的发生. | 心肌梗塞是一种非常严重的疾病，如果未得到及时的治疗，可能会导致严重的后果，如心脏衰竭、心律失常、心力衰竭等。因此，一旦确诊为心肌梗塞，应该立即就医，接受专业的治疗。治疗方法包括药物治疗、手术治疗和介入治疗等。具体治疗方案应该根据患者的具体情况和病情严重程度来制定。如果您或您身边的人患有心肌梗塞，请及时就医并遵医嘱进行治疗。同时，预防心肌梗塞的发生也非常重要，如保持良好的生活习惯、控制高血压、糖尿病等慢性疾病，以及避免吸烟、饮酒等不良习惯。 |
| 对于使用NOACs的患者接种COVID-疫苗, 需要注意哪些事项? | 对于使用NOACs的患者接种COVID-19疫苗, 需要特别注意以下几点:<br/>1. 建议在接种前咨询医生, 了解是否适合接种.<br/>2. 在接种期间和接种后一周内, 应避免进行剧烈运动、重体力劳动等活动, 以防出现出血等不良反应.<br/>3. 如果患者正在服用NOACs药物, 应该告知医生, 以便医生根据具体情况决定是否可以接种疫苗.<br/>4. 如果患者有任何不适或疑虑, 应及时就医并告知医生疫苗接种的情况. | 1. 患者在接受NOAC治疗期间应避免接种疫苗.<br/>2. 如果必须进行疫苗接种, 建议咨询医生的意见并遵循以下指导: <br/>a) 在开始任何一种疫苗之前, 需要告知您的医疗团队您正在服用NOAC药物; <br/>b) NOAC药物可能会影响某些疫苗的效果和安全性, 因此请务必告诉您的医疗团队您正在使用的所有药物(包括非处方药、草药等); <br/>c) 对于那些已经完成NOAC治疗并且没有出现严重副作用的患者来说, 他们可以考虑接种新冠疫苗. 但是, 如果他们在过去6个月内曾发生过严重的出血事件或血栓形成史, 则不应该接种新冠疫苗.<br/>3. 请注意, 如果您有任何疑问或担忧, 请及时与您的医疗团队联系以获取更多信息. | 对于使用NOACs的患者，接种COVID-19疫苗时需要注意以下几点：<br/>1. 请先咨询医生：使用NOACs的患者应该在接种前咨询医生，了解疫苗的禁忌症和注意事项，以及是否需要调整药物剂量或停止使用药物。<br/>2. 疫苗接种前停止使用NOACs：在接种疫苗前，应该停止使用NOACs药物，以确保疫苗的有效性。<br/>3. 接种前检查：在接种前，应该进行血液检查，以确保身体状况良好，没有其他疾病或过敏反应。<br/>4. 接种后观察：在接种后，应该密切观察身体反应，如发热、头痛、肌肉疼痛、疲劳等，如果出现任何不适症状，应该及时就医。<br/>5. 疫苗接种后继续使用NOACs：在接种后，应该继续按照医生的建议使用NOACs药物，以确保药物的安全性和有效性。<br/><br/>总之，使用NOACs的患者在接种COVID-19疫苗前需要咨询医生，并按照医生的建议进行接种。同时，在接种后需要密切观察身体反应，如果出现任何不适症状，应该及时就医。 |

### 致谢

## 👨‍💻 研发团队

本项目由**华东理工大学 X-D Lab**课题组发起, 
| 主要分工 | 参与同学 |
| :----: | :---- |
| 模型训练 | [颜鑫](https://github.com/thomas-yanxin)、[王明](https://github.com/w-sunmoon) |
| 模型测试 |  |
| 数据构建 |  |

同时，受到以下项目及平台的大力支持, 在此表示感谢!
1. [LLaMA-Efficient-Tuning](https://github.com/hiyouga/LLaMA-Efficient-Tuning): 提供微调代码
2. [OpenI启智社区](https://openi.pcl.ac.cn/): 提供模型训练算力
3. [魔搭ModelScope](https://modelscope.cn/home): 提供训练思路和模型存储
4. [文心一格](https://yige.baidu.com/): 生成模型logo

```

@Misc{llama-efficient-tuning, 
  title = {LLaMA Efficient Tuning}, 
  author = {hiyouga}, 
  howpublished = {\url{https://github.com/hiyouga/LLaMA-Efficient-Tuning}}, 
  year = {2023}
}

```

<a href="https://github.com/thomas-yanxin/Sunsimiao/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=thomas-yanxin/Sunsimiao" />
</a>  

### 免责申明

本仓库所有开源代码及模型均遵循GPL-3.0许可认证. 开源模型可能存在以下局限. 欢迎商业交流与合作!

1. **孙思邈中文医疗大模型**存在固有的局限性, 可能产生错误的、有害的、冒犯性的或其他不良的输出. 用户在关键或高风险场景中应谨慎行事, 不要使用这些模型作为最终决策参考, 以免导致人身伤害、财产损失或重大损失. 

2. **孙思邈中文医疗大模型**由**baichuan-7B**模型微调而得, 按"原样"提供, 在任何情况下, 作者、贡献者或版权所有者均不对因软件或使用或其他软件交易而产生的任何索赔、损害赔偿或其他责任(无论是合同、侵权还是其他原因)承担责任.

3. 使用**孙思邈中文医疗大模型**即表示您同意这些条款和条件, 并承认您了解其使用可能带来的潜在风险. 您还同意赔偿并使作者、贡献者和版权所有者免受因您使用**孙思邈中医药大模型**而产生的任何索赔、损害赔偿或责任的影响.

### 引用

```

@misc{Sunsimiao, 
  author={Xin Yan, Dong Xue*}, 
  title = {Sunsimiao: Chinese Medical Large Language Model}, 
  year = {2023}, 
  publisher = {GitHub}, 
  journal = {GitHub repository}, 
  howpublished = {\url{https://github.com/X-D-Lab/Sunsimiao}}, 
}
```
