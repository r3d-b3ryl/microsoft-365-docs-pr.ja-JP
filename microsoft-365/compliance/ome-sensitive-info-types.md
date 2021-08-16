---
title: 機密情報の種類ポリシーを作成するには、次のOffice 365 Message Encryption
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
description: このページを使用して、組織の機密情報の種類ポリシーを作成するOffice 365 Message Encryption。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1cf9432adbe2cecb889d6e744077d8807ae556089b388f321e1348199e1ee165
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53879289"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>メッセージ暗号化を使用して組織の機密情報の種類ポリシーを作成する

メール フロー ルールExchangeまたはデータ損失防止 (DLP) のいずれかを使用して、機密情報の種類ポリシーを作成Office 365 Message Encryption。 メール フロー ルールExchange作成するには、管理センター (EAC) または PowerShell Exchangeを使用できます。

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>EAC でメール フロー ルールを使用してポリシーを作成するには

管理センター (EAC) Exchangeサインインし、[メール フロールール]**に移動**  >  **します**。 [ルール] ページで、ルールを適用するルールをOffice 365 Message Encryption。 メッセージまたは添付ファイルに特定のキーワードや機密情報の種類が存在するなどの条件に基づいてルールを作成できます。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>PowerShell でメール フロー ルールを使用してポリシーを作成するには

組織でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用し、Windows PowerShellセッションを開始し、Exchange Online。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 ポリシーを作成Set-IRMConfiguration、New-TransportRuleコマンドレットを使用します。

## <a name="example-mail-flow-rule-created-with-powershell"></a>PowerShell で作成されたメール フロー ルールの例

PowerShell で次のコマンドを実行して、Exchange メール フロー ルールを作成し、電子メールまたは添付ファイルに次の機密情報の種類が含まれている場合は、組織外に送信された電子メールを暗号化専用オプションで自動的に暗号化します。

- ABA ルーティング番号
- クレジット カード番号
- 麻薬取締局 (DEA) 番号
- 米国/英国 passport number
- 米国の銀行口座番号
- 米国の個人納税者識別番号 (ITIN)
- 米国の社会保障番号 (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

詳細については [、「Set-IRMConfiguration」](/powershell/module/exchange/set-irmconfiguration) および [「New-TransportRule」を参照してください](/powershell/module/exchange/new-transportrule)。

## <a name="how-recipients-access-attachments"></a>受信者が添付ファイルにアクセスする方法

Microsoft がメッセージを暗号化すると、受信者は暗号化された電子メールにアクセスして開く際に、添付ファイルに無制限にアクセスできます。

## <a name="to-prepare-for-this-change"></a>この変更の準備をするには

該当するエンドユーザー向けドキュメントとトレーニング資料を更新して、組織のユーザーをこの変更に備える必要があります。 必要に応Office 365 Message Encryption、これらのリソースをユーザーと共有します。

- [PC 用に暗号化されたメッセージを送信、表示、返信Outlookする](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365Essentials ビデオ: Office暗号化](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>監査ログでこれらの変更を表示する

Microsoft 365アクティビティを監査し、管理者が使用できます。 操作は 'New-TransportRule' であり、コンプライアンス センターのセキュリティ監査ログ検索のサンプル監査エントリ&以下に示します。

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>機密情報の種類ポリシーを無効またはカスタマイズするには

Exchange メール フロー ルールを作成したら、Exchange 管理センター [](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)   >   (EAC) の [メール フロー ルール] に移動してルールを無効にし、[送信機密メールの暗号化 (アウトボックス ルール *)*] を無効にします。