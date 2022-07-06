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
description: データ損失防止 (DLP) ポリシーを設計する方法について説明します
ms.openlocfilehash: 32204659da3adcc2fd868568bf3a7bd909e5f2f9
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66623011"
---
# <a name="design-a-data-loss-prevention-policy"></a>データ損失防止ポリシーを設計する

ポリシーを実装する前に時間を取って設計すると、目的の結果にすばやく到達し、意図しない問題が少なくなります。作成してから、試用版とエラーだけでチューニングするよりも少なくなります。 ポリシーデザインを文書化しておくと、通信、ポリシーレビュー、トラブルシューティング、およびさらなるチューニングにも役立ちます。

<!--, but excessive tuning to get the intended results can be time consuming.

 if you have to do a lot of tuning to get a policy to yield the intended results can be time consuming .-->

Microsoft Purview DLP を初めて使用する場合は、ポリシーの設計を開始する前に、次の記事を実行すると便利です。

- [Microsoft Purview データ損失防止について学習](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)する - この記事では、データ損失防止規範と Microsoft による DLP の実装について説明します
- [データ損失防止 (DLP) を計画](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp) する - この記事に従って、次のことを行います。
  - [利害関係者を特定する](dlp-overview-plan-for-dlp.md#identify-stakeholders)
  - [保護する機密情報のカテゴリについて説明する](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
  - [目標と戦略を設定する](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
- [データ損失防止ポリシー リファレンス](dlp-policy-reference.md#data-loss-prevention-policy-reference) - この記事では、DLP ポリシーのすべてのコンポーネントと、それぞれがポリシーの動作に与える影響について説明します

## <a name="policy-design-overview"></a>ポリシー設計の概要

[ポリシーの設計](#policy-design-process)は、主に[ビジネス ニーズを明確に定義し、ポリシー意図ステートメントで文書化し、](#define-intent-for-the-policy)[それらのニーズをポリシー構成にマッピングすることです](#map-business-needs-to-policy-configuration)。 計画フェーズで行った決定を使用して、ポリシー設計の決定の一部を通知します。

### <a name="define-intent-for-the-policy"></a>ポリシーの意図を定義する

1 つのステートメントで、持つすべてのポリシーのビジネス意図を要約できる必要があります。 このステートメントを開発すると、組織内の会話が促進され、完全に具体化されると、このステートメントはポリシーをビジネス目的に直接リンクし、ポリシー設計のロードマップを提供します。 [データ損失防止の計画 (DLP) に関する](dlp-overview-plan-for-dlp.md#overview-of-planning-process)記事の手順は、ポリシーの意図に関する声明を開始するのに役立ちます。

[DLP ポリシーの構成の概要](dlp-learn-about-dlp.md#dlp-policy-configuration-overview)から、すべての DLP ポリシーには次のものが必要です。

- 監視する内容を選択する
- 監視する場所を選択する
- アイテムに適用するポリシーに一致する必要がある条件を選択する
- ポリシー条件が満たされたときに実行するアクションを選択する

たとえば、4 つの質問すべてに対する回答を提供する意図ステートメントの架空の最初の草案を次に示します。

*"Microsoft は米国に拠点を置く組織であり、OneDrive/SharePoint に格納されている HIPPA の対象となる機密性の高い医療情報を含む Office ドキュメントを検出し、Teams チャットやチャネル メッセージで共有されているその情報から保護し、承認されていないサード パーティとの共有を全員に制限する必要があります。*

ポリシー設計を開発するときに、ステートメントを変更して拡張する可能性があります。

### <a name="map-business-needs-to-policy-configuration"></a>ビジネス ニーズをポリシー構成にマップする

下書きステートメントの例を分解し、DLP ポリシー構成ポイントにマップしましょう。

|Statement|構成に関する質問に回答し、構成マッピングを行う|
|---|---|
|"Microsoft は米国を拠点とする組織であり、HIPPA の対象となる機密性の高い医療情報を含む Office ドキュメントを検出する必要があります。|- **監視対象**: Office ドキュメント、 [米国健康保険法 (HIPAA)](what-the-dlp-policy-templates-include.md#us-health-insurance-act-hipaa) テンプレートを使用する </br>- **一致条件**: (事前構成済みだが編集可能) - 項目には、米国 SSN および薬物執行機関 (DEA) 番号、国際分類の病気 (ICD-9-CM)、国際分類の病気 (ICD-10-CM) が含まれています。コンテンツは組織外のユーザーと共有されます  </br> - 会話を駆動して、 [信頼レベル](sensitive-information-type-learn-about.md#more-on-confidence-levels)や [インスタンス数](dlp-policy-reference.md#content-contains) (漏えい許容度と呼ばれる) などの検出のトリガーしきい値を明確にします。|
|...OneDrive/SharePoint に格納され、Teams チャットとチャネル メッセージが共有されているその情報から保護します。...|- **監視する場所**: OneDrive サイトと SharePoint サイト、Teams チャット/チャネル アカウント、または配布グループを含めるか除外して  [、場所のスコープ](dlp-policy-reference.md#locations) を設定します。|
|...すべてのユーザーがそれらのアイテムを承認されていないサード パーティと共有できないように制限します。|- **実行するアクション**: アクセスの制限 [を追加](dlp-policy-reference.md#actions)*するか、Microsoft 365 の場所でコンテンツを暗号化* します </br> - 共有制限、通知やアラートなどの認識アクション、ブロックアクションのユーザーオーバーライドを許可するなどのユーザーエンパワーメントアクションなど、ポリシーがトリガーされたときに実行するアクションに関する会話を促進します|

この例では、DLP ポリシーのすべての構成ポイントを網羅しているわけではなく、展開する必要があります。 ただし、独自の DLP ポリシー意図ステートメントを開発するときに、正しい方向に考える必要があります。

> [!IMPORTANT]
> 選択した場所は、機密情報の種類、秘密度ラベル、保持ラベル、および使用可能なアクションを使用できるかどうかに影響します。 [データ損失防止ポリシーリファレンスを参照してください](dlp-policy-reference.md#data-loss-prevention-policy-reference)。

## <a name="policy-design-process"></a>ポリシー設計プロセス

1. [データ損失防止の計画 (DLP)](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp) の手順を完了します。この記事では、次の作業を行います。
   1. [関係者を特定する](dlp-overview-plan-for-dlp.md#identify-stakeholders)
   1. [保護する機密情報のカテゴリについて説明する](dlp-overview-plan-for-dlp.md#describe-the-categories-of-sensitive-information-to-protect)
   1. [目標と戦略を設定する](dlp-overview-plan-for-dlp.md#set-goals-and-strategy)
   1. [ポリシー展開計画を定義する](dlp-overview-plan-for-dlp.md#policy-deployment)

2. DLP ポリシーのすべてのコンポーネントと、それぞれがポリシーの動作にどのような影響を与えるかを理解できるように、 [データ損失防止ポリシーリファレンス](dlp-policy-reference.md#data-loss-prevention-policy-reference) について理解します。

3. [DLP ポリシー テンプレートに含まれる内容について](what-the-dlp-policy-templates-include.md#what-the-dlp-policy-templates-include)理解します。

4. 主要な利害関係者と共にポリシー意図ステートメントを開発します。 この記事の前の例を参照してください。

5. このポリシーが DLP ポリシー戦略全体にどのように適合するかを決定します。

   > [!IMPORTANT]
   > ポリシーは、作成後に名前を変更することはできません。 ポリシーの名前を変更する必要がある場合は、目的の名前を持つ新しいポリシーを作成し、古い名前を削除する必要があります。 そのため、すべてのポリシーが現在使用する名前付け構造を決定します。

6. ポリシー意図ステートメント内の項目を構成オプションにマップします。

7. 開始するポリシー テンプレート、定義済み、またはカスタムのポリシー テンプレートを決定します。

8. ポリシーを作成する前に、テンプレートを確認し、必要なすべての情報を組み立てます。 ポリシー意図ステートメントで説明されていない構成ポイントがいくつか存在する可能性があります。 いいですよ。 不足している構成ポイントの要件を把握するために、関係者に戻るします。

9. すべてのポリシー設定の構成を文書化し、関係者と確認します。 ポリシー意図ステートメントのマッピングを構成ポイントに再利用できます。これで完全に具体化されます。

10. ポリシーの下書き[を作成](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)し、[ポリシーの展開](dlp-overview-plan-for-dlp.md#policy-deployment)計画に戻ります。

<!--## Policy design examples

|Customer business needs description|approach|
|---|---|
|**Contoso Bank** is in a highly regulated industry and has  many different types of sensitive items in many different locations. </br> - knows which types of sensitive information are top priority. </br> - must minimize business disruption as policies are rolled out. </br> -  has IT resources and can hire experts to help plan, design deploy </br> - has a premier support contract with Microsoft|- Take the time to understand what regulations they must comply with and how they are going to comply. </br> -Take the time to understand the better together value of the Microsoft 365 Information Protection stack </br> - Develop sensitivity labeling scheme for prioritized items and apply </br> - Involve business process owners </br>- Design/code policies, deploy in test mode, train users </br>- repeat|
|**TailSpin Toys** doesn’t know what they have or where it is, and have little to no resource depth. They use Teams, OneDrive for Business and Exchange extensively.|- Start with simple policies on the prioritized locations. </br>- Monitor what gets identified </br>- Apply sensitivity labels accordingly </br>- Refine policies, train users|
|**Fabrikam** is a small startup and wants to protect its intellectual property, and must move quickly. They are willing to dedicate some resources, but can't afford to hire outside experts. </br>- Sensitive items are all in Microsoft 365 OneDrive for Business/SharePoint </br>- Adoption of OneDrive for Business and SharePoint is slow, employees/shadow IT use DropBox and Google drive to share/store items </br>- Employees value speed of work over data protection discipline </br>- Customer splurged and bought all 18 employees new Windows 10 devices|- Take advantage of the default DLP policy in Teams </br>- Use restricted by default setting for SharePoint items </br>- Deploy policies that prevent external sharing </br>- Deploy policies to prioritized locations </br>- Deploy policies to Windows 10 devices </br>- Block uploads to non-OneDrive for Business cloud storage|

1. For example:
    1. Identify your volume thresholds that your company deems to be low-risk (leakage tolerance), perhaps from unintentional sharing and is an opportunity to educate users and the threshold that is concerning or high-risk for your company that may need immediate attention.
    - example volume: “Low risk” for Contoso is 1 credit card number, perhaps it was a personal card that was shared carelessly
    - example volume: “High risk” for Contoso is 2 or more credit card numbers. It doesn’t feel like a common scenario that an employee would engage in accidentally

– For each of the sensitive information types listed out, list out **who should have access to that data when it’s generated** and **what type of activities should be allowable with that data**

  <!--(Perhaps this is where we can provide some basic categories, templates, activities and actions that are supported by Microsoft. Some of these items are not discoverable until you are deeper within a policy creation flow. If we provide, we should time stamp it for “last updated” or “as of xx/xx/xxx”)
– (Show table with parent-child relationships between categories, templates and sensitive info types that Microsoft supports) Should be gathered from GA Compliance environment-->

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

|Statement|Configuration question answered and configuration mapping|
|---|---|
|We are a national healthcare provider based in the U.S. We need to protect our patient’s personal information...|- **What to monitor**: All available item types, use the [U.S. Health Insurance Act (HIPAA)](what-the-dlp-policy-templates-include.md#us-health-insurance-act-hipaa) template. </br>- **Conditions for a match**: (preconfigured but editable) - item contains full names, physical addresses, driver's license number, U.S. SSN
|...and prevent it from egressing outside of our company’s borders...|- **Actions to take**: Block anyone outside the organization from accessing items, block unintentional sharing by internal users with anyone outside the org.|
|...We want to limit access to our patient’s personal information to only authorized personnel, like our physicians and billing department from our on-premises devices...|- **Actions to take**: - Block access to items, block all activities (upload to cloud, copy to clipboard, copy to USB, copy to network share, access by restricted app, print, copy/move via Bluetooth, copy/move via remote desktop) from Windows devices.  </br> - **Where to monitor**: in all Microsoft 365 locations
|...We've determined that any single instance of any of each information type in any item is not a data risk, but it is a risk when two or more occur in a single item....|- **Conditions for a match**: (preconfigured but editable) any single item contains more than one of these or any two or more of these:  Full Name, U.S. Social Security Number, Drug Enforcement Agency (DEA) number, International Classification of Diseases (ICD-9-CM), International Classification of Diseases (ICD-10-CM), Physical Address, U.S. driver's license number. For example, two instanced of Full Name or one instance of a U.S. Social Security Number along with one instance of Drug Enforcement Agency (DEA) number will trigger a match.

   , content is shared with people outside my organization  </br> - drives conversations to clarify the triggering threshold for detection like [confidence levels](sensitive-information-type-learn-about.md#more-on-confidence-levels), and [instance count](dlp-policy-reference.md#content-contains) (called leakage tolerance).|
|...that are stored in OneDrive/SharePoint and protect against that information being shared Teams chat and channel messages...|- **Where to monitor**:  [Location scoping](dlp-policy-reference.md#locations) by including or excluding OneDrive and SharePoint sites and Teams chat/channel accounts or distribution groups.|
|...and restrict everyone from sharing those items with unauthorized third parties."|- **Actions to take**: [You add](dlp-policy-reference.md#actions) *Restrict access or encrypt the content in Microsoft 365 locations* </br> - drives conversation on what actions to take when a policy is triggered including protective actions like sharing restrictions, awareness actions like notifications and alerts, and user empowerment actions like allow user overrides of a blocking action|

-->

## <a name="see-also"></a>関連項目

- [データ損失防止について](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [データ損失防止ポリシー (DLP) のサポート](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [データ損失防止ポリシー リファレンス](dlp-policy-reference.md#data-loss-prevention-policy-reference)
- [データ損失防止ポリシーヒントのリファレンス](dlp-policy-tips-reference.md#data-loss-prevention-policy-tips-reference)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)
