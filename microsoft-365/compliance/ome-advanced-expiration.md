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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: カスタム Office 365 Advanced Message Encryptionを使用してメールの有効期限を設定することで、電子メールのセキュリティを拡張するために使用します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1213ecf48ee9bd2e04accdd13aaf3ecd74d3faba
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152936"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Office 365 Advanced Message Encryption 機能を使って暗号化されたメールの有効期限を設定する

Office 365 Advanced Message Encryptionは[、Microsoft 365 Enterprise E5、Office 365 E5、Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home)(非営利スタッフ価格)、Office 365 Enterprise E5 (非営利スタッフ価格)、および Office 365 Education A5 に含まれています。 組織に Office 365 Advanced Message Encryption を含めないサブスクリプションがある場合は、Microsoft 365 E5 Compliance SKU アドオンを使用して Microsoft 365 E3、Microsoft 365 E3 (Nonprofit)スタッフの価格設定Office 365 Advanced Compliance SKU アドオン(Microsoft 365 E3、Microsoft 365 E3(非営利スタッフ価格)、または SKU のOffice 365します。

ユーザーが OME ポータルを使用して暗号化されたメールにアクセスする外部受信者に送信するメールに対して、メッセージの有効期限を使用できます。 Windows PowerShell で有効期限を指定するカスタム ブランド テンプレートを使用して、受信者に OME ポータルを使用して組織から送信された暗号化されたメールを表示して返信を強制します。

グローバル管理者Office 365、会社のブランドを適用して組織の電子メール メッセージの外観をカスタマイズするときに、これらの電子メール メッセージの有効期限を指定することもできます。 このOffice 365 Advanced Message Encryption、組織から送信される暗号化された電子メール用に複数のテンプレートを作成できます。 テンプレートを使用すると、受信者がユーザーから送信されたメールにアクセスできる期間を制御できます。

有効期限が設定されたメールをエンド ユーザーが受信すると、ラッパー メールに有効期限が表示されます。 ユーザーが期限切れのメールを開こうとすると、OME ポータルにエラーが表示されます。

メールの有効期限は、外部受信者にのみ設定できます。

カスタム Office 365 Advanced Message Encryptionを適用すると、Office 365 はテンプレートを適用するメール フロー ルールに適合するメールにラッパーを適用します。 さらに、カスタム ブランドを使用する場合にのみ有効期限を使用できます。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>PowerShell を使用してメールの有効期限を強制するカスタム ブランド テンプレートを作成する

1. [ConnectグローバルExchange Onlineアクセス](/powershell/exchange/connect-to-exchange-online-powershell)許可を持つアカウントを使用して PowerShell を作成する方法について説明します。

2. このコマンドレットをNew-OMEConfigurationします。

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

ここで、

- `Identity` は、カスタム テンプレートの名前です。

- `ExternalMailExpiryInDays` 受信者が期限切れになる前にメールを保持できる日数を識別します。 1 ~ 730 日間の任意の値を使用できます。

## <a name="more-information-about-office-365-advanced-message-encryption"></a>詳細については、Office 365 Advanced Message Encryption

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Office 365 Advanced Message Encryption 機能を使って暗号化されたメールを無効にする](revoke-ome-encrypted-mail.md)

- [メッセージ ポリシーとコンプライアンス サービスの説明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)