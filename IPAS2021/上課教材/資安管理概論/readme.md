
## 資訊安全管理概論

- 1.資訊安全管理概念
``` 
   資訊安全目標_CIA   
     CIA: 機密性(Confidentiality) 完整性(Integrity) 可用性(Availability)
     各種破壞CIA的情境
     保護CIA的方法
     AAA ==> 驗證(Authentication) 授權(Authorization) 可歸責(Accountability)
     CIAAAA
     其他資安基本觀念 
        可靠度(Reliability)
        不可否認性(Non-repudiation)
        邊界與分類(Boundary and classification)
        職務區隔(Segregation of duties, SOD) 
        縱深防禦(Layered defense, defense in depth)
        單一脆弱點(Single point of failure, SPOF)
        阿奇里斯腱(Achilles heel)
        木桶理論(Bucker principle）
        僅知原則(Need to know)
   資訊安全管理系統|ISMS|Information Security Management System
     導入ISMS的目的
     導入ISMS的過程與程序
     導入ISMS的關鍵主題與事項
   相關法規概論與遵循
   隱私權保護與智慧財產權
```
- 2.資產與風險管理
  - 2-1.資產分類分級與盤點
    - 資訊資產
    - 資訊資產分類(類型)及分級(低中高)
    - 資訊資產分級的目的
    - 資訊資產分級的盤點施作方式
  - 2-2.風險評鑑與風險處理
    - 國際標準與架構
      - NIST RMF(Risk Management Framework)
      - ISO 27005(2018)
      - ISO 31000 "Risk management – Principles and guidelines on implementation    
    - 風險管理(risk management):定義
    - 風險管理流程(Process)
    - 全景建立
      - 風險評估準則(Risk Evaluation Criteria)
      - 衝擊準則(Impact Criteria)
      - 風險接受準則(Risk Acceptance Criteria
    - 風險評鑑(Risk assessment)
      - 風險評鑑的方法 ==> 可區分為「高階風險評鑑」與「詳細風險評鑑」作法

    - 風險處理(Risk treatment) ==> 殘餘風險|剩餘風險
      - 四種風險處理{策略|模式}:
        - 1.Risk reduction = 風險降低(風險修改)
        - 2.Risk retention = 風險保留(風險接受)
        - 3.Risk avoidance = 風險避免
        - 4.Risk sharing = 風險分擔(風險轉移) 
    - 風險接受(Risk acceptance)
- 3.存取控制、加解密與金鑰管理
  - 3-1.存取控制與身份認證
    - 存取控制(Access_control)
      - 定義
      - 三大存取控制類型: 
        - 1.實體類控制(Physical Controls) 
        - 2.技術類控制(Technical Controls) 
        - 3.管理類控制(Administrative Controls)
      - [存取控制 seven功能](http://cisspstudy.blogspot.com/2007/05/types-of-access-control.html)
        - 防禦性(Preventive)
        - 偵測性(Detective)
        - 矯正性(Corrective)
        - 嚇阻性(Deterrent)
        - 復原性(Recovery)
        - 補償性(Compensation) 
      - 存取控制管理
      - Access control models存取控制模型
        - 自主存取控制(Discretionary access control)(DAC)
        - 強制存取控制(Mandatory access control) (MAC)
        - 角色存取控制(Role-based access control)(RBAC)
        - 規則存取控制(Rule-Based Access Control) (RAC)
        - 屬性存取控制(Attribute-based access control)(ABAC)
    - 身份認證(Authentication)
      - 定義
      - 三大因子(factors) 
        - 所知之事，你知| Something you `know`| the knowledge factors
        - 所持之物，你有(Something you `have`)| the ownership factors:
        - 所具之形，你是 |Something you `are` | the inherence factors
      - Single-factor authentication[單因子驗證] vs  Multi-factor authentication[多因子驗證]
    - 各種驗證方法與鑑別技術
      - 1_通行碼身分鑑別技術
      - 2_一次性通行碼(One-time Password)| 動態通行碼 鑑別技術 
      - 3_詰問與回應身分鑑別技術
      - 4_生物特徵鑑別技術 
  - 3-2.加解密與金鑰生命週期

- 4.事故管理與營運持續
  - 4-1.事件與事故管理
  - 4-2.備援與營運持續
