---
title: データ損失防止ポリシーを設計する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: データ損失防止 (DLP) ポリシーを設計する方法について学習する
ms.openlocfilehash: 14e9fbb5efd20ddcf3d0a47da41a0cce89c88cee
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526320"
---
# <a name="design-a-data-loss-prevention-policy"></a>データ損失防止ポリシーを設計する

ポリシーを実装する前に、ポリシーを設計する時間を取って、意図しない問題を作成してから試行錯誤だけで調整するよりも、目的の結果を迅速かつ少なくすることができます。 ポリシー設計を文書化すると、コミュニケーション、ポリシー レビュー、トラブルシューティング、さらに調整に役立ちます。

<!--, but excessive tuning to get the intended results can be time consuming.

 if you have to do a lot of tuning to get a policy to yield the intended results can be time consuming .-->

DLP の使用をMicrosoft 365する場合は、ポリシーの設計を開始する前に、以下の記事を参照してください。

- [データ損失防止の詳細](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) - この記事では、データ損失防止の規律と Microsoft による DLP の実装について説明します。
- [データ損失防止 (DLP) を計画する](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp) - この記事で作業することで、次の作業を行います。
    - [関係者を特定する](dlp-overview-plan-for-dlp.md#identify-stakeholders)
    - [保護する機密情報のカテゴリを説明する](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
    - [目標と戦略を設定する](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
- [データ損失防止ポリシーリファレンス](dlp-policy-reference.md#data-loss-prevention-policy-reference) - この記事では、DLP ポリシーのすべてのコンポーネントと、各コンポーネントがポリシーの動作に与える影響について説明します。

## <a name="policy-design-overview"></a>ポリシー設計の概要

[ポリシーの設計は、](#policy-design-process)主にビジネス ニーズを[](#define-intent-for-the-policy)明確に定義し、ポリシーインテントステートメントで文書化し、それらのニーズをポリシー構成[にマッピングする方法です](#map-business-needs-to-policy-configuration)。 計画フェーズで行った決定を使用して、ポリシー設計の決定の一部を通知します。 

### <a name="define-intent-for-the-policy"></a>ポリシーの意図を定義する 

1 つのステートメントに含むすべてのポリシーのビジネス意図を要約できる必要があります。 このステートメントを開発すると、組織内での会話が進み、完全に肉付けされた場合、このステートメントはポリシーをビジネス目的に直接リンクし、ポリシー設計のロードマップを提供します。 「データ損失防止計画 [(DLP)」](dlp-overview-plan-for-dlp.md#overview-of-planning-process) の記事の手順は、ポリシーの意図に関するステートメントを開始するのに役立ちます。  

DLP ポリシー構成 [の概要では、すべての](dlp-learn-about-dlp.md#dlp-policy-configuration-overview) DLP ポリシーで次の操作が必要です。

- 監視する対象を選択する
- 監視する場所を選択する
- アイテムに適用するポリシーに一致する必要がある条件を選択する
- ポリシー条件が満たされた場合に実行するアクションを選択する 

たとえば、4 つの質問に対する回答を提供する、架空の最初の意図ステートメントの下書きを次に示します。 

*「弊社は米国に拠点を置く組織であり、OneDrive/SharePoint に保存されている HIPPA がカバーする機密性の高い医療情報を含む Office ドキュメントを検出し、Teams チャットメッセージやチャネル メッセージで共有される情報から保護し、すべてのユーザーが承認されていない第三者と共有するのを制限する必要があります。* 

ポリシー設計を開発する場合、ステートメントを変更して拡張する可能性があります。

### <a name="map-business-needs-to-policy-configuration"></a>ビジネス ニーズをポリシー構成にマップする

下書きステートメントの例を切り取り、DLP ポリシー構成ポイントにマップします。

|Statement  |構成に関する質問の回答と構成マッピング  |
|---------|---------|
| 「米国に拠点を置く組織であり、HIPPA がカバーするOfficeを含むドキュメントを検出する必要があります。  |- **監視対象: ドキュメント** Office、米国健康保険法 [(HIPAA) テンプレートを使用](what-the-dlp-policy-templates-include.md#us-health-insurance-act-hipaa)する </br>- **一** 致の条件: (事前構成済みですが編集可能) - アイテムには、米国 SSN および麻薬取締局 (DEA) 番号、国際疾病分類 (ICD-9-CM)、国際疾病分類 (ICD-10-CM) が含まれる場合、コンテンツは組織外のユーザーと共有されます。  </br> - 会話を駆動して、信頼度などの検出のトリガー[](sensitive-information-type-learn-about.md#more-on-confidence-levels)しきい値、およびインスタンス[数 (漏洩](dlp-policy-reference.md#content-contains)許容値と呼ばれる) を明確にします。|
|...に保存され、OneDrive/SharePointメッセージで共有される情報Teams保護します。。 |- **監視する場所**: [チャット](dlp-policy-reference.md#locations)/チャネル アカウントまたは配布グループOneDrive、SharePointサイトTeamsを含む、または除外することで、場所のスコープを設定します。 |
|...すべてのユーザーがこれらのアイテムを承認されていない第三者と共有するのを制限します。  | - **実行するアクション**: [アクセスの制限を](dlp-policy-reference.md#actions)*追加するか、ユーザーの場所でコンテンツMicrosoft 365します。* </br> - 共有制限などの保護アクション、通知やアラートなどの認識アクション、ブロックアクションのユーザーオーバーライドを許可するなどのユーザーエンパワーメントアクションなど、ポリシーがトリガーされた場合に実行するアクションに関する会話を推進します。 |

この例では、DLP ポリシーのすべての構成ポイントをカバーしているので、展開する必要があります。 しかし、独自の DLP ポリシー意図ステートメントを開発する場合は、正しい方向に考える必要があります。

> [!IMPORTANT]
> 選択した場所は、機密情報の種類、機密ラベル、保持ラベル、および使用可能なアクションを使用できるかどうかに影響を与えます。 「データ [損失防止ポリシーリファレンス」を参照してください](dlp-policy-reference.md#data-loss-prevention-policy-reference)。

## <a name="policy-design-process"></a>ポリシー設計プロセス

1. 以下の手順を実行します。
    1. [データ損失防止 (DLP) を計画する](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp) - この記事で作業することで、次の作業を行います。
        1. [関係者を特定する](dlp-overview-plan-for-dlp.md#identify-stakeholders)
        1. [保護する機密情報のカテゴリを説明する](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
        1. [目標と戦略を設定する](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
        1. [ポリシー展開計画の定義](dlp-overview-plan-for-dlp.md#policy-deployment)

1. DLP ポリシーのすべての [コンポーネントと](dlp-policy-reference.md#data-loss-prevention-policy-reference) 、各コンポーネントがポリシーの動作に与える影響を理解するために、データ損失防止ポリシーリファレンスについて理解してください。

1. DLP ポリシー テンプレートに [含まれるものについて理解してください](what-the-dlp-policy-templates-include.md#what-the-dlp-policy-templates-include)。

1. 主要な関係者と一緒にポリシーの意図に関するステートメントを開発します。 この記事の前の例を参照してください。

1. このポリシーが DLP ポリシー戦略全体に適合する方法を決定します。

> [!IMPORTANT]
> ポリシーの作成後は、ポリシーの名前を変更できません。 ポリシーの名前を変更する必要がある場合は、目的の名前を持つ新しいポリシーを作成し、古い名前を削除する必要があります。 したがって、すべてのポリシーで今使用する名前付け構造を決定します。 

6. ポリシー インテント ステートメント内のアイテムを構成オプションにマップします。

7. 開始するポリシー テンプレート、定義済みポリシー テンプレート、またはカスタム ポリシー テンプレートを決定します。

8. ポリシーを作成する前に、テンプレートを参照し、必要なすべての情報を組み立てます。 ポリシーの意図に関するステートメントで説明されていない構成ポイントがいくつかある可能性があります。 いいですよ。 関係者に戻り、不足している構成ポイントの要件を取り上手に戻します。 

9. すべてのポリシー設定の構成を文書化し、関係者と確認します。 ポリシー インテント ステートメントのマッピングを構成ポイントに再使用できます。これで完全に肉付けされます。

10. [下書き](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy) ポリシーを作成し、ポリシー展開計画 [に戻](dlp-overview-plan-for-dlp.md#policy-deployment) します。

<!--## Policy design examples

|Customer business needs description  | approach  |
|---------|---------|
|**Contoso Bank** is in a highly regulated industry and has  many different types of sensitive items in many different locations. </br> - knows which types of sensitive information are top priority. </br> - must minimize business disruption as policies are rolled out. </br> -  has IT resources and can hire experts to help plan, design deploy </br> - has a premier support contract with Microsoft| - Take the time to understand what regulations they must comply with and how they are going to comply. </br> -Take the time to understand the better together value of the Microsoft 365 Information Protection stack </br> - Develop sensitivity labeling scheme for prioritized items and apply </br> - Involve business process owners </br>- Design/code policies, deploy in test mode, train users </br>- repeat|
|**TailSpin Toys** doesn’t know what they have or where it is, and have little to no resource depth. They use Teams, OneDrive for Business and Exchange extensively.     |- Start with simple policies on the prioritized locations. </br>- Monitor what gets identified </br>- Apply sensitivity labels accordingly </br>- Refine policies, train users       |
|**Fabrikam** is a small startup and wants to protect its intellectual property, and must move quickly. They are willing to dedicate some resources, but can't afford to hire outside experts. </br>- Sensitive items are all in Microsoft 365 OneDrive for Business/SharePoint </br>- Adoption of OneDrive for Business and SharePoint is slow, employees/shadow IT use DropBox and Google drive to share/store items </br>- Employees value speed of work over data protection discipline </br>- Customer splurged and bought all 18 employees new Windows 10 devices     |- Take advantage of the default DLP policy in Teams </br>- Use restricted by default setting for SharePoint items </br>- Deploy policies that prevent external sharing </br>- Deploy policies to prioritized locations </br>- Deploy policies to Windows 10 devices </br>- Block uploads to non-OneDrive for Business cloud storage      |


1. For example:
    1. Identify your volume thresholds that your company deems to be low-risk (leakage tolerance), perhaps from unintentional sharing and is an opportunity to educate users and the threshold that is concerning or high-risk for your company that may need immediate attention.
    - example volume: “Low risk” for Contoso is 1 credit card number, perhaps it was a personal card that was shared carelessly
    - example volume: “High risk” for Contoso is 2 or more credit card numbers. It doesn’t feel like a common scenario that an employee would engage in accidentally



–   For each of the sensitive information types listed out, list out **who should have access to that data when it’s generated** and **what type of activities should be allowable with that data**


  <!--(Perhaps this is where we can provide some basic categories, templates, activities and actions that are supported by Microsoft. Some of these items are not discoverable until you are deeper within a policy creation flow. If we provide, we should time stamp it for “last updated” or “as of xx/xx/xxx”)
–   (Show table with parent-child relationships between categories, templates and sensitive info types that Microsoft supports) Should be gathered from GA Compliance environment-->

<!--


> [!TIP] The more locations you include ensures broader application of the policy and more consistent coverage. If you include locations that are mostly used for internal collaboration, the responsiveness of collaboration may be impacted.


- whether the protective actions you need are supported throught the associated location or if you need to compromise to extend coverage
    - also usefule for identifying the most restrictive actions available 
    - (we shouldn't mention here that the "content contains" condition is the primary staple for a DLP policy and should be utilized as a starting point for policy creation. The other workload-specific conditions can be ustilized as an extended or granular control of company's DLP policy. Useful for when "too much" data is being restricted and known sensitive data typically falls under certain conditions.)
    - (We can mention here that their quantitative goal such as "protect X% of data across all locations while maintaining x productivity" can be monitored throught alerts or reports. If protection is too high of working against their established goals, they can come back to policy and tweak their conditions/actions)
- Finally, you should have a union of what, hwo and when to be covered which will easily map to generating a live policy via Microsoft DLP. 
- 
5. At this stage you should asses how you should start this policy. ***LINK OUT TO DEPLOYING A POLICY COVERED IN THE PLANNING TOPIC TOO***
    - Test: your company is very large, conservative or the actions established are pretty restrictive
    - Test w/ notifications: same as above, but you get to test out investigation cadence or volume
    - Live: immediately start this policy in your environment. Useful for when data protection is needed immediately, such as a reactive policy creation, or if you're confident in your planning, or if the risk is low (liek audit actions, etc.)
    - keep it off:
-->

<!--## Policy Design Examples

Here are some examples of more detailed policy intent statement to configuration mappings.

*We are a national healthcare provider based in the U.S. We need to protect our patient’s personal information and prevent it from egressing outside of our company’s borders. We want to limit access to our patient’s personal information to only authorized personnel, like our physicians and billing department from our on-premises devices. We've determined that any single instance of any of each information type in any item is not a data risk, but it is a risk when two or more occur in a single item. We have a Microsoft 365 E5 subscription and want to protect all locations and first party apps that are available to us because we can’t afford to have any data leaks. If an event occurs or is prevented, we want to alert our compliance admin and educate our end-users where necessary.*

|Statement  |Configuration question answered and configuration mapping  |
|---------|---------|
| We are a national healthcare provider based in the U.S. We need to protect our patient’s personal information...|- **What to monitor**: All available item types, use the [U.S. Health Insurance Act (HIPAA)](what-the-dlp-policy-templates-include.md#us-health-insurance-act-hipaa) template. </br>- **Conditions for a match**: (preconfigured but editable) - item contains full names, physical addresses, driver's license number, U.S. SSN
| ...and prevent it from egressing outside of our company’s borders... |- **Actions to take**: Block anyone outside the organization from accessing items, block unintentional sharing by internal users with anyone outside the org.|
|...We want to limit access to our patient’s personal information to only authorized personnel, like our physicians and billing department from our on-premises devices...| - **Actions to take**: - Block access to items, block all activities (upload to cloud, copy to clipboard, copy to USB, copy to network share, access by restricted app, print, copy/move via Bluetooth, copy/move via remote desktop) from Windows devices.  </br> - **Where to monitor**: in all Microsoft 365 locations
| ...We've determined that any single instance of any of each information type in any item is not a data risk, but it is a risk when two or more occur in a single item....| - **Conditions for a match**: (preconfigured but editable) any single item contains more than one of these or any two or more of these:  Full Name, U.S. Social Security Number, Drug Enforcement Agency (DEA) number, International Classification of Diseases (ICD-9-CM), International Classification of Diseases (ICD-10-CM), Physical Address, U.S. driver's license number. For example, two instanced of Full Name or one instance of a U.S. Social Security Number along with one instance of Drug Enforcement Agency (DEA) number will trigger a match.

   , content is shared with people outside my organization  </br> - drives conversations to clarify the triggering threshold for detection like [confidence levels](sensitive-information-type-learn-about.md#more-on-confidence-levels), and [instance count](dlp-policy-reference.md#content-contains) (called leakage tolerance).|
|...that are stored in OneDrive/SharePoint and protect against that information being shared Teams chat and channel messages... |- **Where to monitor**:  [Location scoping](dlp-policy-reference.md#locations) by including or excluding OneDrive and SharePoint sites and Teams chat/channel accounts or distribution groups. |
|...and restrict everyone from sharing those items with unauthorized third parties."  | - **Actions to take**: [You add](dlp-policy-reference.md#actions) *Restrict access or encrypt the content in Microsoft 365 locations* </br> - drives conversation on what actions to take when a policy is triggered including protective actions like sharing restrictions, awareness actions like notifications and alerts, and user empowerment actions like allow user overrides of a blocking action |

-->


## <a name="see-also"></a>関連項目

- [データ損失防止について](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [データ損失防止 (DLP) の計画](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [データ損失防止ポリシーリファレンス](dlp-policy-reference.md#data-loss-prevention-policy-reference)
- [データ損失防止ポリシーヒントのリファレンス](dlp-policy-tips-reference.md#data-loss-prevention-policy-tips-reference)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)