LLM10: 模型盗窃
 
此条目指的是恶意行为者或 APT 对 LLM 模型进行未经授权的访问和泄露。当专有的大语言模型模型（有价值的知识产权）被泄露、物理盗窃、复制或提取权重和参数以创建功能等效时，就会出现这种情况。 LLM 模型盗窃的影响可能包括经济和品牌声誉损失、竞争优势受到侵蚀、未经授权使用模型或未经授权访问模型中包含的敏感信息。
 
随着语言模型变得越来越强大和普遍，大语言模型被盗代表了一个重大的安全问题。组织和研究人员必须优先考虑强有力的安全措施来保护其大语言模型模型，确保其知识产权的机密性和完整性。采用包括访问控制、加密和持续监控在内的全面安全框架对于减轻与 LLM 模型盗窃相关的风险以及保护依赖 LLM 的个人和组织的利益至关重要。
 
威胁的常见示例
 
1. 攻击者利用公司基础设施中的威胁，通过网络或应用程序安全设置的错误配置来获得对其 LLM 模型存储库的未经授权的访问。
2. 一种内部威胁场景，心怀不满的员工泄露模型或相关工件。
3. 攻击者使用精心设计的输入和提示注入技术来查询模型 API，以收集足够数量的输出来创建影子模型。
4. 恶意攻击者能够绕过 LLM 的输入过滤技术来执行旁道攻击，并最终将模型权重和架构信息收集到远程控制资源。
5. 模型提取的攻击向量涉及使用特定主题的大量提示来查询 LLM。然后，大语言模型的输出可用于微调另一个模型。不过，对于这次攻击，有几点需要注意: 
a. 攻击者必须生成大量有针对性的提示。如果提示不够具体，LLM 的输出将毫无用处。
b. LLM 的输出有时可能包含幻觉答案，这意味着攻击者可能无法提取整个模型，因为某些输出可能是无意义的。
c. 通过模型提取 100% 复制 LLM 是不可能的。然而，攻击者将能够复制部分模型。
6. 功能模型复制的攻击向量涉及通过提示使用目标模型来生成合成训练数据（一种称为“自指导”的方法），然后使用它并微调另一个基础模型以生成功能等效项。这绕过了示例 5 中使用的传统基于查询的提取的限制，并已成功用于使用 LLM 训练另一个 LLM 的研究。尽管在本研究的背景下，模型复制并不是一种攻击。攻击者可以使用该方法通过公共 API 复制专有模型。
 
使用被盗模型作为影子模型，可用于进行对抗性攻击，包括未经授权访问模型中包含的敏感信息，或在未检测到的情况下使用对抗性输入进行实验，以进一步进行高级提示注入。
 
如何预防
 
1. 实施强大的访问控制（例如: RBAC 和最小权限规则）和强大的身份验证机制，以限制对 LLM 模型存储库和培训环境的未经授权的访问。
a. 对于前三个常见示例尤其如此，这可能由于内部威胁、错误配置和/或对包含 LLM 模型、权重和架构的基础设施的安全控制薄弱而导致此威胁，其中恶意行为者可能从内部或外部渗透进入。
b. 供应链管理跟踪、验证和依赖性威胁是防止供应链攻击的重要焦点主题。
2. 限制大语言模型对网络资源、内部服务和 API 的访问。
a. 这在所有常见的示例中尤为明显，因为它涵盖了内部风险和威胁，但最终也控制着语言模型应用程序所能“访问的内容”，因此可能是一种用于防止侧信道攻击机制或预防措施。
3. 定期监控和审核与 LLM 模型存储库相关的访问日志和活动，以及时检测和响应任何可疑或未经授权的行为。
4. 通过治理、跟踪和审批工作流程自动化 MLOps 部署，以加强基础设施内的访问和部署控制。
5. 实施控制和缓解策略，以减轻和/或降低提示注入技术导致侧通道攻击的风险。
6. 在适用的情况下对 API 调用进行速率限制和/或过滤器，以降低从 LLM 应用程序中泄露数据的风险，或实施技术来检测来自其他监控系统的（EG、DLP）提取活动。
7. 实施对抗性鲁棒性训练，以帮助检测提取查询并加强物理安全措施。
8. 将水印框架实施到大语言模型生命周期的嵌入(embedding)和检测阶段。
 
攻击场景示例
 
1. 攻击者利用公司基础设施中的威胁未经授权访问其 LLM 模型存储库。攻击者继续窃取有价值的 LLM 模型，并使用它们启动竞争性语言处理服务或提取敏感信息，从而对公司造成重大财务损失。
2. 心怀不满的员工泄露了模型或相关工件。这种场景的公开曝光增加了攻击者对灰盒对抗性攻击或直接窃取可用财产的了解。
3. 攻击者使用精心选择的输入查询 API，并收集足够数量的输出来创建影子模型。
4. 供应链中存在安全控制故障，导致专有模型信息的数据泄露。
5. 恶意攻击者绕过 LLM 的输入过滤技术和前导码来执行旁道攻击，并将模型信息检索到其控制下的远程控制资源。
 
参考链接
 
1. Meta强大的AI语言模型已在网上泄露:  https ://www.theverge.com/2023/3/8/23629362/meta-ai-language-model-llama-leak-online-misuse
2. 逃跑的骆驼 | Meta 的 LLaMA NLP 模型如何泄露:  https://www.deeplearning.ai/the-batch/how-metas-llama-nlp-model-leaked/
3. 我知道你看到了什么:  https://arxiv.org/pdf/1803.05847.pdf
4. D-DAE: 防御渗透模型提取攻击:  https://www.computer.org/csdl/proceedings-article/sp/2023/933600a432/1He7YbsiH4c
5. 针对模型提取攻击的全面防御框架:  https://ieeexplore.ieee.org/document/10080996
6. 羊驼毛: 强大的、可复制的指令遵循模型:  https://crfm.stanford.edu/2023/03/13/alpaca.html
7. 水印如何帮助减轻大语言模型的潜在风险？:  https://www.kdnuggets.com/2023/03/watermarking-help-mitigate-pottial-risks-llms.html
 
