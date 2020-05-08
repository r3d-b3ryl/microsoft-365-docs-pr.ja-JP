---
title: メッセージの暗号化を使用して組織の機密情報の種類のポリシーを作成する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Office 365 メッセージの暗号化を使用して、組織の機密情報の種類のポリシーを作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7ba94923c1f8c6ade6b7bf494636c562b4cc4102
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165958"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>メッセージの暗号化を使用して組織の機密情報の種類のポリシーを作成する

Exchange メールフロールールまたはデータ損失防止 (DLP) のいずれかを使用して、Office 365 メッセージの暗号化を使用して機密情報の種類のポリシーを作成できます。 Exchange メールフロールールを作成するには、Exchange 管理センター (EAC) または PowerShell のどちらかを使用できます。

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>EAC でメールフロールールを使用してポリシーを作成するには

Exchange 管理センター (EAC) にサインインし、[**メールフロー** > ] [**ルール**] に移動します。 [ルール] ページで、Office 365 メッセージの暗号化を適用するルールを作成します。 特定のキーワードの存在や、メッセージまたは添付ファイル内の機密情報の種類などの条件に基づいてルールを作成することができます。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>PowerShell でメールフロールールを使用してポリシーを作成するには

組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。 New-transportrule コマンドレットと新しいコマンドレットを使用して、ポリシーを作成します。

## <a name="example-mail-flow-rule-created-with-powershell"></a>PowerShell を使用して作成されたメールフロールールの例

メールまたは添付ファイルに次の機密情報の種類が含まれている場合は、PowerShell で次のコマンドを実行して、組織外から送信されたメールを*暗号化専用*ポリシーで自動的に暗号化する Exchange メールフロールールを作成します。

- ABA ルーティング番号
- クレジットカード番号
- 医薬品執行機関 (DEA) 番号
- 米国/英国 passport number
- 米国の銀行口座番号
- 米国の個人納税者識別番号 (ITIN)
- 米国の社会保障番号 (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

詳細については、「 [new-transportrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps) [」を参照して](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps)ください。

## <a name="how-recipients-access-attachments"></a>受信者が添付ファイルにアクセスする方法

Microsoft がメッセージを暗号化すると、受信者は暗号化された電子メールにアクセスして開くときに、添付ファイルに無制限でアクセスできるようになります。

## <a name="to-prepare-for-this-change"></a>この変更を準備するには

この変更に関して組織内のユーザーを準備するために、適用可能なエンドユーザードキュメントおよびトレーニング資料を更新することが必要な場合があります。 必要に応じて、これらの Office 365 メッセージ暗号化リソースをユーザーと共有します。

- [Outlook for PC で暗号化されたメッセージを送信、表示、および返信する](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365 Essentials Video: Office メッセージの暗号化](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>監査ログでのこれらの変更の表示

Microsoft 365 は、このアクティビティを監査して、管理者が使用できるようにします。 この操作は ' New-transportrule ' であり、セキュリティ & コンプライアンスセンターでの監査ログの検索からのサンプルの監査エントリのスニペットは以下のとおりです。

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>機密情報の種類のポリシーを無効にする、またはカスタマイズするには

Exchange メールフロールールを作成したら、exchange 管理センター (EAC) の**メールフロー** > **ルール**に移動し、[*送信機密メールを暗号化する (標準のルール)*] ルールを無効にして、[ルールを無効にしたり、編集](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)したりすることができます。
