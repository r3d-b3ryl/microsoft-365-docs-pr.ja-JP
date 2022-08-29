---
title: 疑わしいパスワード スプレー関連の IP アドレス アクティビティ アラート
description: 疑わしいパスワード スプレー関連の IP アドレス アクティビティのアラート の評価を行い、アラートを確認し、攻撃を修復してネットワークを保護するための推奨されるアクションを実行します。
keywords: インシデント, アラート, 調査, 分析, 応答, 相関関係, 攻撃, デバイス, ユーザー, 365, Microsoft, m365, パスワード, スプレー, アラートの分類, アラートの採点, クラウド アプリ, 疑わしい IP
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-dgali
author: dgali297
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: 621f52f4dc400d8a3afe56d3f6f08005547d7014
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360634"
---
# <a name="suspicious-password-spray-related-ip-activity"></a>不審なパスワード スプレー関連の IP アクティビティ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

脅威アクターは、パスワード推測手法を使用してユーザー アカウントにアクセスします。 パスワード スプレー攻撃では、脅威アクターは、さまざまなアカウントに対して最もよく使用されるパスワードのいくつかに頼る可能性があります。 多くのユーザーが既定のパスワードと脆弱なパスワードを引き続き使用しているため、攻撃者はパスワード スプレーを使用してアカウントを侵害することに成功しました。

このガイドは、IP アドレスに危険なラベルが付けられたり、パスワード スプレー攻撃に関連付けられたり、不明な場所からサインインしたユーザーや、予期しない多要素認証 (MFA) プロンプトを受け取ったユーザーなど、疑わしい原因不明のアクティビティが検出されたインスタンスを調査するのに役立ちます。 このガイドは、セキュリティ オペレーション センター (SOC) や、アラートの確認、処理、管理、分類を行う IT 管理者などのセキュリティ チーム向けです。 このガイドは、アラートを [真陽性 (TP) または偽陽性 (FP)](investigate-alerts.md) として迅速に分類し、TP の場合は推奨されるアクションを実行して攻撃を修復し、セキュリティ リスクを軽減するのに役立ちます。

このガイドを使用する目的の結果は次のとおりです。

- パスワード スプレー IP アドレスに関連付けられているアラートを、悪意のある (TP) アクティビティまたは偽陽性 (FP) アクティビティとして識別しました。

- IP アドレスがパスワード スプレー攻撃を実行している場合は、必要なアクションを実行しました。

## <a name="investigation-steps"></a>調査手順

このセクションには、アラートに対応し、組織をさらなる攻撃から保護するための推奨されるアクションを実行するための詳細なガイダンスが含まれています。

### <a name="1-review-the-alert"></a>1. アラートを確認する

アラート キュー内のパスワード スプレー アラートの例を次に示します。

:::image type="content" source="../../media/alert-grading-playbook-password-spray/fig1-password-spray-alert.png" alt-text="Microsoft Defender 365 アラートのスクリーンショット。" lightbox="../../media/alert-grading-playbook-password-spray/fig1-password-spray-alert.png":::

これは、脅威インテリジェンス ソースに従ってブルート フォースまたはパスワード スプレー試行に関連付けられている可能性がある IP アドレスから発生した疑わしいユーザー アクティビティがあることを意味します。

### <a name="2-investigate-the-ip-address"></a>2. IP アドレスを調査する
-   IP から発信された [アクティビティ](microsoft-365-security-center-defender-cloud-apps.md) を確認します。

    - **ほとんどの場合、サインインの試行は失敗しましたか?**

    - **サインイン試行の間隔は疑わしいと思われますか?** 自動パスワード スプレー攻撃は、試行の間隔が一定である傾向があります。

    - **[MFA](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365) プロンプトを使用してサインインするユーザーまたは複数のユーザーの試行が正常に行われますか?** これらの試行の存在は、IP が悪意を持たないことを示している可能性があります。

    - **レガシ プロトコルは使用されますか?** POP3、IMAP、SMTP などのプロトコルを使用すると、パスワード スプレー攻撃を実行しようとする可能性があります。 [アクティビティ ログ](/defender-cloud-apps/activity-filters#ip-address-insights)のユーザー エージェント (デバイスの種類) で検索`Unknown(BAV2ROPC)`すると、レガシ プロトコルの使用が示されます。 アクティビティ ログを確認するときは、次の例を参照できます。 このアクティビティは、他のアクティビティとさらに関連付ける必要があります。

        :::image type="content" source="../../media/alert-grading-playbook-password-spray/fig2-password-spray-alert.png" alt-text="デバイスの種類を示す Microsoft Defender 365 インターフェイスのスクリーンショット。" lightbox="../../media/alert-grading-playbook-password-spray/fig2-password-spray-alert.png":::

        _図 1.[デバイスの種類] フィールドには、Microsoft 365 Defenderのユーザー エージェントが表示`Unknown(BAV2ROPC)`されます。_ 
    - **匿名プロキシまたは Tor ネットワークの使用を確認します。** 脅威アクターは、多くの場合、これらの代替プロキシを使用して情報を非表示にするため、トレースが困難になります。 ただし、すべてのプロキシを使用して悪意のあるアクティビティと関連付けるわけではありません。 より適切な攻撃インジケーターを提供する可能性がある他の不審なアクティビティを調査する必要があります。
    - IP アドレスは仮想プライベート ネットワーク (VPN) から送信されますか? VPN は信頼できますか? **IP が VPN から発信されたかどうかを確認し、RiskIQ などのツールを使用して、その背後にある組織を確認** します。[](https://community.riskiq.com/learn-more/enterprise) 
    - **同じサブネット/ISP を持つ他の IP を確認します。** パスワード スプレー攻撃は、同じサブネット/ISP 内の多くの異なる IP から発生することがあります。
-   **テナントの IP アドレスは共通ですか?** アクティビティ ログを確認して、テナントが過去 30 日間に IP アドレスを見たかどうかを確認します。
-   **テナント内の IP から発生したその他の不審なアクティビティまたはアラートを検索します。** 検索するアクティビティの例としては、サインインが正常に試行された後の電子メールの削除、転送ルールの作成、ファイルのダウンロードなどがあります。
-   RiskIQ などのツールを使用して **、IP アドレスのリスク スコアを確認** します。
    
### <a name="3-investigate-suspicious-user-activity-after-signing-in"></a>3. サインイン後に疑わしいユーザー アクティビティを調査する
疑わしい IP が認識されたら、サインインしたアカウントを確認できます。 アカウントのグループが侵害され、IP またはその他の同様の IP からのサインインに正常に使用された可能性があります。

アラートの時刻の前後に IP アドレスからのサインインに成功したすべての試行をフィルター処理します。 次に、サインイン後に、そのようなアカウントで悪意のあるアクティビティや異常なアクティビティを検索します。 
-   ユーザー アカウントアクティビティ

    **パスワード スプレー アクティビティの前にあるアカウント内のアクティビティが疑わしくないことを検証します。** たとえば、一般的な場所または ISP に基づいて異常なアクティビティがあるかどうかを確認します。アカウントが以前に使用していなかったユーザー エージェントを使用している場合、他のゲスト アカウントが作成された場合、悪意のある IP からサインインしたアカウントの後に他の資格情報が作成された場合などです。
-   アラート
    
    **ユーザーがパスワード スプレー アクティビティの前に他のアラートを受け取ったかどうかを確認します。** これらのアラートを表示すると、ユーザー アカウントが侵害される可能性があることを示します。 たとえば、不可能な旅行アラート、頻度の低い国からのアクティビティ、不審なメール削除アクティビティなどがあります。
-   インシデント

    **アラートがインシデントを示す他のアラートに関連付けられているかどうかを確認します。** その場合は、インシデントに他の正のアラートが含まれているかどうかを確認します。

## <a name="advanced-hunting-queries"></a>高度なハンティング クエリ

[高度な捜索](/microsoft-365/security/defender/advanced-hunting-overview) は、ネットワーク内のイベントを調べて脅威インジケーターを見つけ出すクエリベースの脅威検出ツールです。

このクエリを使用して、悪意のある IP からのリスクスコアが最も高いサインインを試みたアカウントを検索します。 このクエリでは、対応するリスク スコアを使用してサインインに成功したすべての試行もフィルター処理されます。
```kusto
let start_date = now(-7d);
let end_date = now();
let ip_address = ""; // enter here the IP address
AADSignInEventsBeta
| where Timestamp between (start_date .. end_date)
| where IPAddress == ip_address
| where isnotempty(RiskLevelDuringSignIn)
| project Timestamp, IPAddress, AccountObjectId, RiskLevelDuringSignIn, Application, ResourceDisplayName, ErrorCode
| sort by Timestamp asc
| sort by AccountObjectId, RiskLevelDuringSignIn
| partition by AccountObjectId ( top 1 by RiskLevelDuringSignIn ) // remove line to view all successful logins risk scores
```
このクエリを使用して、疑わしい IP がサインインしようとしてレガシ プロトコルを使用したかどうかを確認します。
```kusto
let start_date = now(-8h);
let end_date = now();
let ip_address = ""; // enter here the IP address
AADSignInEventsBeta
| where Timestamp between (start_date .. end_date)
| where IPAddress == ip_address
| summarize count() by UserAgent
```
このクエリを使用して、疑わしい IP に関連付けられた過去 7 日間のすべてのアラートを確認します。
```kusto
let start_date = now(-7d);
let end_date = now();
let ip_address = ""; // enter here the IP address
let ip_alert_ids = materialize ( 
        AlertEvidence
            | where Timestamp between (start_date .. end_date)
            | where RemoteIP == ip_address
            | project AlertId);
AlertInfo
| where Timestamp between (start_date .. end_date)
| where AlertId in (ip_alert_ids)
```
このクエリを使用して、侵害された疑いのあるアカウントのアカウント アクティビティを確認します。
```kusto
let start_date = now(-8h);
let end_date = now();
let ip_address = ""; // enter here the IP address
let compromise_users = 
    materialize ( AADSignInEventsBeta
                    | where Timestamp between (start_date .. end_date)
                    | where IPAddress == ip_address
                    | where ErrorCode == 0
                    | distinct AccountObjectId);
CloudAppEvents
    | where Timestamp between (start_date .. end_date)
    | where AccountObjectId in (compromise_users)
    | summarize ActivityCount = count() by AccountObjectId, ActivityType
    | extend ActivityPack = pack(ActivityType, ActivityCount)
    | summarize AccountActivities = make_bag(ActivityPack) by AccountObjectId
```
このクエリを使用して、侵害された疑いのあるアカウントのすべてのアラートを確認します。
```kusto
let start_date = now(-8h); // change time range
let end_date = now();
let ip_address = ""; // enter here the IP address
let compromise_users = 
    materialize ( AADSignInEventsBeta
                    | where Timestamp between (start_date .. end_date)
                    | where IPAddress == ip_address
                    | where ErrorCode == 0
                    | distinct AccountObjectId);
let ip_alert_ids = materialize ( AlertEvidence
    | where Timestamp between (start_date .. end_date)
    | where AccountObjectId in (compromise_users)
    | project AlertId, AccountObjectId);
AlertInfo
| where Timestamp between (start_date .. end_date)
| where AlertId in (ip_alert_ids)
| join kind=innerunique ip_alert_ids on AlertId
| project Timestamp, AccountObjectId, AlertId, Title, Category, Severity, ServiceSource, DetectionSource, AttackTechniques
| sort by AccountObjectId, Timestamp
```
## <a name="recommended-actions"></a>推奨されるアクション

1. [攻撃者の IP アドレスをブロックします。](/azure/active-directory/conditional-access/block-legacy-authentication)
2. ユーザー アカウントの資格情報をリセットします。 
3. 侵害されたアカウントのアクセス トークンを取り消します。
4. [レガシ認証をブロックします。](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy) 
5. アカウント[のセキュリティを強化](/azure/active-directory/authentication/tutorial-enable-azure-mfa)し、パスワード スプレー攻撃によるアカウント侵害を攻撃者にとって困難にする場合は[、ユーザーに MFA を要求](/microsoft-365/business-premium/m365bp-conditional-access)します。 
6. 必要に応じて、侵害されたユーザー アカウントのサインインをブロックします。
## <a name="see-also"></a>関連項目

- [アラートの採点の概要](alert-grading-playbooks.md)
- [アラートの調査](investigate-alerts.md)