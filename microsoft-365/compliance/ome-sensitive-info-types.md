---
title: Office 365 メッセージ暗号化を使用して機密情報の種類のポリシーを作成する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Office 365 メッセージ暗号化を使用して、組織の機密情報の種類ポリシーを作成する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: 0974c30882177eb9fc46c2a2fcf65bc2edb43078
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633435"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>メッセージ暗号化を使用して組織の機密情報の種類ポリシーを作成する

Exchange メール フロー ルールまたは Microsoft Purview データ損失防止 (DLP) のいずれかを使用して、Office 365 Message Encryption を使用して機密情報の種類のポリシーを作成できます。 Exchange メール フロー ルールを作成するには、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター (EAC)</a> または PowerShell を使用します。

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>EAC でメール フロー ルールを使用してポリシーを作成するには

<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>にサインインし、**メール フロー** >  ルールに移動 **します**。 [ルール] ページで、メッセージ暗号化Office 365適用するルールを作成します。 メッセージまたは添付ファイルに特定のキーワードや機密情報の種類が存在するなどの条件に基づいてルールを作成できます。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>PowerShell でメール フロー ルールを使用してポリシーを作成するには

組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用して、powerShell Exchange Online接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 Set-IRMConfigurationコマンドレットとNew-TransportRule コマンドレットを使用してポリシーを作成します。

## <a name="example-mail-flow-rule-created-with-powershell"></a>PowerShell で作成されたメール フロー ルールの例

PowerShell で次のコマンドを実行して、電子メールまたはその添付ファイルに次の機密情報の種類が含まれている場合に、暗号化専用オプションを使用して組織外で送信された電子メールを自動的に暗号化する Exchange メール フロー ルールを作成します。

- ABA ルーティング番号
- クレジット カード番号
- ドラッグ エンフォースメント エージェンシー (DEA) 番号
- 米国/英国 passport number
- 米国の銀行口座番号
- 米国の個人納税者識別番号 (ITIN)
- 米国の社会保障番号 (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

詳細については、「 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) と [New-TransportRule](/powershell/module/exchange/new-transportrule)」を参照してください。

## <a name="how-recipients-access-attachments"></a>受信者が添付ファイルにアクセスする方法

Microsoft がメッセージを暗号化した後、受信者は暗号化されたメールにアクセスして開いたときに、添付ファイルに無制限にアクセスできます。

## <a name="to-prepare-for-this-change"></a>この変更に備えるには

この変更に備えて組織内のユーザーを準備するために、該当するエンド ユーザーのドキュメントとトレーニング資料を更新することができます。 必要に応じて、次のOffice 365メッセージ暗号化リソースをユーザーと共有します。

- [Outlook for PC で暗号化されたメッセージを送信、表示、返信する](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365 Essentials ビデオ: メッセージ暗号化](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>監査ログでこれらの変更を表示する

Microsoft 365 は、このアクティビティを監査し、管理者が利用できるようにします。 この操作は "New-TransportRule" であり、セキュリティ & コンプライアンス センターの監査ログ検索のサンプル監査エントリのスニペットを次に示します。

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"...etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>機密情報の種類ポリシーを無効またはカスタマイズするには

Exchange メール フロー ルールを作成したら、<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>の **メール フロー** > **ルール** に移動し、ルール "*送信機密メールを暗号化する (既定のルール)* を無効にすることで、ルールを [無効または編集](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)できます。
