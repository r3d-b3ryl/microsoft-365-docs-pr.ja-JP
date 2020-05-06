---
title: Office 365 Advanced Message Encryption 機能を使って暗号化されたメールの有効期限を設定する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Office 365 の高度なメッセージ暗号化機能が Office 365 メッセージ暗号化 (OME) の上にあるため、電子メールのセキュリティを拡張するには、カスタムブランド化されたテンプレートを使用して、メールの有効期限を設定します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f555e707cb377033c3bf643785e18b9203be0560
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036060"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Office 365 Advanced Message Encryption 機能を使って暗号化されたメールの有効期限を設定する

Office 365 の高度なメッセージの暗号化は、 [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非営利団体の価格)、Office 365 Enterprise E5 (非営利スタッフの価格)、office の365教育用 A5 に含まれています。 Office 365 Advanced Message Encryption が含まれていないサブスクリプションが組織にある場合は、microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、または Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、または Office の 365 Sku で、Microsoft 365 E5 コンプライアンス SKU アドオンを使用して購入できます。

OME ポータルを使用して暗号化された電子メールにアクセスする外部の受信者に送信するユーザーが電子メールでメッセージの有効期限を使用できます。 受信者が OME ポータルを使用して、組織によって送信される暗号化された電子メールを、Windows Powershell で有効期限を指定するカスタムブランド化テンプレートを使用して表示および返信できるようにします。

O365 全体管理者は、組織の電子メールメッセージの外観をカスタマイズするために会社のブランドを適用するときに、これらの電子メールメッセージの有効期限を指定することもできます。 Office 365 Advanced Message Encryption を使用すると、組織から発信される暗号化された電子メール用に複数のテンプレートを作成できます。 テンプレートを使用すると、受信者がユーザーによって送信されたメールにアクセスできる期間を制御できます。

エンドユーザーが有効期限が設定されたメールを受信すると、ユーザーにはラッパーの電子メールの有効期限が表示されます。 ユーザーが期限切れメールを開こうとすると、OME ポータルにエラーが表示されます。

電子メールの有効期限は、外部の受信者にのみ設定できます。

Office 365 Advanced Message Encryption では、カスタムブランドを適用するたびに、Office 365 は、テンプレートを適用するメールフロールールに適合するラッパーを電子メールに適用します。 また、カスタムブランド化を使用する場合にのみ、有効期限を使用できます。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>PowerShell を使用してメールの有効期限を強制するカスタムブランド化テンプレートを作成する

1. 組織のグローバル管理者のアクセス許可を持つアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。

2. OMEConfiguration 新しいコマンドレットを実行します。

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

ここで、

- `Identity`は、カスタムテンプレートの名前です。

- `ExternalMailExpiryInDays`受信者が期限切れになる前にメールを保持できる日数を指定します。 1から730日までの任意の値を使用できます。

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Office 365 の詳細なメッセージの暗号化に関する詳細情報

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Office 365 Advanced Message Encryption 機能を使って暗号化されたメールを無効にする](revoke-ome-encrypted-mail.md)

- [メッセージポリシーとコンプライアンスサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
