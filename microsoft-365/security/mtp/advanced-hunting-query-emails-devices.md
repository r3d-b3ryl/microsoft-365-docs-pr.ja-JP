---
title: 高度な捜索を使用してデバイスとメール全体で脅威を見つける
description: デバイスとメールを対象とした一般的な捜索シナリオとサンプル クエリを説明します。
keywords: 高度な捜索、Office365 データ、Windows デバイス、Office 365 メールの正規化、メール、脅威の捜索、サイバー脅威の捜索、検索、クエリ、テレメトリ、Microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 0bbcef72fa305819c9f8e0813cfcdfd6c2b0fff3
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234726"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a>デバイスとメール全体で脅威を捜索する

**適用対象:**
- Microsoft Threat Protection



[Microsoft Threat Protection](advanced-hunting-overview.md) の高度な捜索を使用すると、Windows デバイスおよび Office 365 メール全体で積極的に脅威を捜索できます。 デバイスとメールの両方を対象としたクエリの作成方法を検討する上で役立つ捜索シナリオとサンプル クエリをいくつか紹介します。

## <a name="obtain-user-accounts-from-email-addresses"></a>メール アドレスからユーザー アカウントを取得する
[デバイスとメールを対象とする複数のテーブル](advanced-hunting-schema-tables.md)全体に対してクエリを作成する場合、送信者または受信者のメール アドレスからユーザー アカウント名を取得する必要があります。 これを行うには、メール アドレスからの *local-host* を使用します。

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

この正規化の手法は、以下のシナリオで使用されます。

## <a name="hunting-scenarios"></a>捜索のシナリオ

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>既知の悪意のある送信者からのファイルがデバイスに存在するかどうかを確認する
悪意のあるファイルを送信するメール アドレスが判明している場合、このクエリを実行すると、その送信者からのファイルがデバイスに存在するかどうかを確認できます。 このクエリは、マルウェア配布キャンペーンの影響を受けたデバイスの数を特定する目的などに使用できます。

```kusto
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>悪意のあるメール受信後のログオン試行を確認する
このクエリは、既知の悪意のあるメールの受信後 30 分以内に受信者が実行したログオン試行のうち、最新のもの 10 件を見つけます。 このクエリを使用することで、メールの受信者のアカウントが侵害されたかどうかを確認できます。

```kusto
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
DeviceLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>既知の悪意のある送信者からのメール受信後の PowerShell アクティビティを確認する
悪意のあるメールには多くの場合、PowerShell コマンドを実行して追加のペイロードを配信するドキュメントや特別に細工した添付ファイルが含まれます。 既知の悪意のあるユーザーから送信されたメールに気付いた場合、このクエリを使用することで、その送信者からのメールの受信後 30 分以内に発生した PowerShell アクティビティを表示および確認できます。  

```kusto
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
DeviceProcessEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>関連項目
- [積極的に脅威を検索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
