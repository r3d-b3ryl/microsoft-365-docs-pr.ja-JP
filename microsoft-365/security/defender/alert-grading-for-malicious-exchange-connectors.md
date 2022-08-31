---
title: 悪意のある交換コネクタのアラート評価
description: 悪意のある交換コネクタ アクティビティから評価受信者に警告し、ネットワークを悪意のある攻撃から保護します。
keywords: インシデント、アラート、調査、分析、応答、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 16f168fc772e4b4c9e7f48221dbd14039690ba83
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480235"
---
# <a name="alert-grading-for-malicious-exchange-connectors"></a>悪意のある交換コネクタのアラート評価

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

攻撃者は、侵害された交換コネクタを使用し、正当なメールを装って、疑いを持たない受信者にスパムやフィッシング メールを大量に送信します。 コネクタが侵害されているため、通常、メールは受信者によって信頼されます。 この種のフィッシング メールは、フィッシング キャンペーンや法人メール侵害 (BEC) シナリオの一般的なベクトルです。 したがって、このようなメールは、受信者の侵害が成功する可能性が高いため、厳重に監視する必要があります。

プレイブックは、悪意のあるアクターによって悪意のあるコネクタがセットアップ/展開されるインスタンスの調査に役立ちます。 したがって、攻撃を修復し、そこから生じるセキュリティ リスクを軽減するために必要な措置を講じます。 プレイブックは、セキュリティ オペレーション センター (SOC) などのセキュリティ チームや、アラートの確認、処理/管理、評価を行う IT 管理者が利用できます。 プレイブックは、アラートを真陽性 (TP) または偽陽性 (FP) として評価するのに役立ちます。 TP がある場合、プレイブックは攻撃を修復するために必要な推奨アクションを実行します。

プレイブックを使用した結果は次のとおりです。

- 悪意のある (TP) または良性 (FP) としてのアラートの決定。 
    - 悪意のある場合は、環境から悪意のあるコネクタを修復/削除します。

## <a name="exchange-connectors"></a>"Exchange Connectors/Exchange コネクタ"

交換コネクタは、Microsoft 365 または Office 365 組織との間でメールがやり取りされる方法をカスタマイズする手順のコレクションです。 通常、ほとんどの Microsoft 365 および Office 365 組織では、通常のメール フローにコネクタは必要ありません。

コネクタは、リモートのメール システムと Office 365 (O365) または O365、およびオンプレミスのメール システムの間でメール トラフィックをルーティングするために使用されます。

## <a name="malicious-exchange-connectors"></a>悪意のある交換コネクタ

攻撃者は、既存の交換コネクタを侵害するか、管理者を侵害し、フィッシングまたはスパム/バルク メールを送信して新しいコネクタを設定する可能性があります。 

悪意のあるコネクタの典型的な兆候は、メール トラフィックとそのヘッダーを見るとわかります。 たとえば、P1 (ヘッダー送信者) と P2 (エンベロープ送信者) の送信者アドレスが一致せず、送信者の AccountObjectId に関する情報がないコネクタ ノードから、メール トラフィックが観察された場合です。

このアラートは、送信者に関連する情報が利用できないことに加えて、メール送信アクティビティが疑わしいと思われるメール フローのインスタンスを識別しようとします。 
 
## <a name="playbook-workflow"></a>プレイブックのワークフロー

悪意のある交換コネクタを特定するには、次の順序に従う必要があります。

- メールを送信しているアカウントを特定します。
  - アカウントが侵害されているように見えますか?
- チェックするメールをリレーしているコネクタを特定します。
  - コネクタが大量のメールを送信することになっている場合は?
  - コネクタが最近変更または作成された場合は?
- メールは内部のメール アドレスに送信されますか?
  - メールは外部アドレスに送信されますか (スプレー アンド プレイ スパム)?
  - メールは、顧客またはベンダーに属する外部アドレスに送信されますか (サプライ チェーン タイプの攻撃)?
- FROM ヘッダーとエンベロープ送信者のドメインが同じか異なるかを確認します。

## <a name="investigating-malicious-connectors"></a>悪意のあるコネクタの調査

このセクションでは、アラートを調査し、このインシデントによるセキュリティ リスクを修復する手順について説明します。

- コネクタが悪い (悪意のある) 動作を示しているかどうかを判断します。
  - 異常なメール トラフィックを示すイベントを探して、新しい交換コネクタが最近追加されたかどうかを特定します。
    - 観察されたメール トラフィックについて、メール アカウントが異常なメール トラフィックの原因であるかどうかを調べて、メール アカウントが危険にさらされているかどうかを判断します。
  - 悪意のあるアーティファクト (不適切なリンク/添付ファイル) を含むメール コンテンツを探します。
  - 環境の一部ではないドメインを探します。 
- メール アカウントが侵害されていないことを確認します。 環境で最近追加または変更されたコネクタを特定します。
- 次のものを探します。 
  - P1送信者 (メール ヘッダー送信者) と P2 送信者 (エンベロープ送信者) のフィールド値に、不一致がないか確認します。
  - SenderObjectId フィールドの空の値。
- 利用統計情報を使用して、次の点に注意してください。
  - 悪意のあるコネクタから送信されたメールの NetworkMessageId (メッセージ ID)。 
  - コネクタの作成日、最終変更日。
  - メール トラフィックが観察されるコネクタの IP アドレス。
  
## <a name="advanced-hunting-queries"></a>高度な追求クエリ

[高度な追求](/microsoft-365/security/defender/advanced-hunting-overview?)クエリを使用して、アラートに関連する情報を収集し、アクティビティが疑わしいかどうかを判断できます。 

次のテーブルにアクセスできることを確認します。

|**Table Name/テーブル名**  |**説明**  |
|---------|---------|
|EmailEvents| メール フローに関連する情報が含まれます。|
|CloudAppEvents|ユーザー アクティビティの監査ログが含まれます。|
|IdentityLogonEvents|すべてのユーザーのログイン情報が含まれます。|

## <a name="references"></a>関連情報

参照用の AHQ サンプル:

- この KQL を実行して、新しいコネクタの作成を確認します。
  ```
  //modify timeWindow to modify the lookback.
  let timeWindow = now(-7d); let timeNow = now();
  CloudAppEvents
  | where Timestamp between (timeWindow .. timeNow)
  | where isnotempty(AccountObjectId)
  | where ActionType == "New-InboundConnector"
  | mvexpand property = RawEventData.Parameters
  | extend ConnectorName = iff(property.Name == "Name", property.Value, ""), 
  IsEnabled = iff((property.Name == "Enabled" and property.Value == "True"), 
  true, false)
  | where isnotempty( ConnectorName) or IsEnabled
  | project-reorder ConnectorName, IsEnabled

  ```  
- Run this KQL to check the volume of events from the alerted connector with time window of before and after the alerts.
  ```
  //modify timeWindow により、ルックバックを変更します。
  let timeWindow = now(-7d); let timeNow = now(); let connectorOperations = pack_array("Set-OutboundConnector", "New-OutboundConnector", "Set-InboundConnector", "New-InboundConnector"); let mailThreshold = 100; //検査とフィルター処理のしきい値を定義する let myConnector= //このコード ブロックを使用して、関連するコネクタを指定する CloudAppEvents | where Timestamp between (timeWindow .. timeNow) | where ActionType has_any (connectorOperations) | mv-expand property = RawEventData.Parameters | where property.Name == "Name" | summarize by ConnectorName=tostring(property.Value) ; EmailEvents | where isnotempty( toscalar (myConnector)) | where Timestamp between (timeWindow .. timeNow) | where isnotempty( SenderObjectId) and isnotempty( Connectors) | where Connectors in (toscalar (myConnector)) | summarize MailCount = dcount(NetworkMessageId) by Connectors, SenderObjectId, bin(Timestamp, 1h) | where MailCount >= mailThreshold
   ```
- Run this KQL to check whether emails are being sent to external domains.
  ```
  //modify timeWindow により、ルックバックを変更します。
  let timeWindow = now(-7d); let timeNow = now(); EmailEvents | where Timestamp between (timeWindow .. timeNow) | where isnotempty( SenderObjectId) | extend RecipientDomain= split(RecipientEmailAddress, "@")[1] | where (SenderFromDomain != RecipientDomain) or (SenderMailFromDomain != RecipientDomain) | where EmailDirection !in ("Intra-org" , "Inbound") //この行にコメントを付けて、すべてのメールフローの方向を調べる
  ```
  - If sent to external domains, who else in the environment is sending similar emails (Could indicate compromised user if recipient is unknown domain).
     ```
     //modify timeWindow により、ルックバックを変更します。
     let timeWindow = now(-7d); let timeNow = now(); let countThreshold= 100; //それに応じてカウントのしきい値を変更する EmailEvents | where Timestamp between (timeWindow .. timeNow) | where isnotempty( SenderObjectId) | extend RecipientDomain= split(RecipientEmailAddress, "@")[1] | where (SenderFromDomain != RecipientDomain) or (SenderMailFromDomain != RecipientDomain) | where EmailDirection !in ("Intra-org" , "Inbound") | summarize MailCount= dcount(NetworkMessageId) by SenderObjectId, SenderFromAddress, SenderMailFromAddress , bin(Timestamp, 1h) | where MailCount > countThreshold
     ```
    - Check the mail content for bad behavior
      - Look at URLs in the email or email having attachments.


## AHQ considerations

Following are the AHQ considerations for protecting the recipients from malicious attack.

- Check for admin logins for those who frequently manage connectors from unusual locations (generate stats and exclude locations from where most successful logins are observed).

  - Look for login failures from unusual locations.

  ```
  //modify timeWindow により、ルックバックを変更します。
  let timeWindow = now(-7d); let timeNow = now(); let logonFail= materialize ( IdentityLogonEvents | where Timestamp between (timeWindow .. timeNow) | where isnotempty(AccountObjectId) | where Application != "Active Directory" | where ActionType == "LogonFailed" | where ISP != "Microsoft Azure" | summarize failedLogonCount=count(), LatestTime = max(Timestamp), EarliestTime = min(Timestamp) by AccountObjectId, Application, ISP, CountryCode, bin(Timestamp, 60s) | where failedLogonCount > 100); // let hasLogonFails = isnotempty(toscalar (logonFail)); let logonFailUsers = materialize ( logonFail | distinct AccountObjectId | take 100); let hasLogonFails = isnotempty(toscalar (logonFailUsers)); let logonSuccess= IdentityLogonEvents | where hasLogonFails | where Timestamp between (timeWindow .. timeNow) | where AccountObjectId in (logonFailUsers) | where Application != "Active Directory" | where ISP != "Microsoft Azure" | where ActionType == "LogonSuccess" | project SuccessTime= Timestamp, ReportId, AccountUpn, AccountObjectId, ISP, CountryCode, Application; logonFail | join kind = innerunique logonSuccess on AccountObjectId, ISP, Application | where SuccessTime between (LatestTime .. (LatestTime + 10s)) | summarize arg_min(SuccessTime, ReportId), EarliestFailedTime=min (EarliestTime), LatestFailedTime=max(LatestTime), failedLogonCount= take_any(failedLogonCount), SuccessLogonCount=count(), ISPSet= make_set(ISP), CountrySet=make_set(CountryCode), AppSet=make_set (Application) by AccountObjectId, AccountUpn | project-rename Timestamp=SuccessTime
  ```

## Recommended actions

Once it’s determined that the observed alert activities are part of TP, classify those alerts and perform the actions below:

- Disable or remove the connector that was found to be malicious.
- If the admin account was compromised, reset the admin’s account credentials. Also, disable/revoke tokens for the compromised admin account and enable multi-factor authentication for all admin accounts.
  - Look for suspicious activities performed by the admin.
- Check for other suspicious activities across other connectors in the environment.
