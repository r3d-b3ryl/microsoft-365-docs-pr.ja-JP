---
title: Microsoft Purview の高度なメッセージの暗号化を使って暗号化されたメールの有効期限を設定する
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
description: Microsoft Purview Advanced Message Encryption を使用して、カスタム ブランド テンプレートを使用して電子メールの有効期限を設定することで、電子メールセキュリティを拡張します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e8689820adc3158ae2a36a4d52ebad0959097b49
ms.sourcegitcommit: 7e0094ddff54bcbe5d691dba58d4c4fb86f8b1a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2022
ms.locfileid: "65188396"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-microsoft-purview-advanced-message-encryption"></a>Microsoft Purview の高度なメッセージの暗号化を使って暗号化されたメールの有効期限を設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview Advanced Message Encryption は[、Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非営利団体スタッフ価格)、Office 365 Enterprise E5 (非営利団体スタッフ価格)、およびOffice 365 Education A5。 Microsoft 365 E3、Microsoft 365 E3 (非営利団体スタッフの価格)、またはOffice 365 Advanced Compliance SKU アドオン用のMicrosoft 365 E5 Compliance SKU アドオンMicrosoft 365 E3、Microsoft 365 E3 (非営利団体スタッフの価格)、またはOffice 365 SKU。

組織に Microsoft Purview Advanced Message Encryption を含まないサブスクリプションがある場合は、Microsoft 365 E3、Microsoft 365 E3 (非営利団体スタッフ価格)、またはMicrosoft 365 E5 Compliance SKU アドオンで購入できます。Microsoft 365 E3、Microsoft 365 E3 (非営利団体スタッフの価格)、またはOffice 365 SKU 用の SKU アドオンをOffice 365 Advanced Complianceします。

メッセージの有効期限は、ユーザーが OME ポータルを使用して暗号化された電子メールにアクセスする外部受信者に送信するメールで使用できます。 受信者に対し、Windows PowerShellで有効期限を指定するカスタム ブランド テンプレートを使用して、組織から送信された暗号化されたメールを表示および返信するために OME ポータルを使用するように強制します。

Office 365グローバル管理者は、会社のブランドを適用して組織の電子メール メッセージの外観をカスタマイズするときに、これらの電子メール メッセージの有効期限を指定することもできます。 Microsoft Purview Advanced Message Encryption を使用すると、組織から送信された暗号化された電子メール用の複数のテンプレートを作成できます。 テンプレートを使用すると、受信者がユーザーから送信されたメールにアクセスできる期間を制御できます。

エンド ユーザーが有効期限が設定されたメールを受信すると、ラッパー電子メールに有効期限が表示されます。 ユーザーが期限切れのメールを開こうとすると、OME ポータルにエラーが表示されます。

外部受信者へのメールの有効期限のみを設定できます。

Microsoft Purview Advanced Message Encryption を使用すると、カスタム ブランドを適用するたびに、テンプレートを適用するメール フロー ルールに適合する電子メールにラッパーがOffice 365によって適用されます。 また、有効期限は、カスタム ブランドを使用する場合にのみ使用できます。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>PowerShell を使用してメールの有効期限を強制するカスタム ブランド テンプレートを作成する

1. [組織内の](/powershell/exchange/connect-to-exchange-online-powershell)グローバル管理者アクセス許可を持つアカウントで PowerShell をExchange Online Connect。

2. New-OMEConfiguration コマンドレットを実行します。

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

ここで、

- `Identity` は、カスタム テンプレートの名前です。

- `ExternalMailExpiryInDays` は、受信者が期限切れになるまでにメールを保持できる日数を示します。 1 ~ 730 日間の任意の値を使用できます。

## <a name="more-information-about-microsoft-purview-advanced-message-encryption"></a>Microsoft Purview Advanced Message Encryption の詳細

- [高度なメッセージ暗号化](ome-advanced-message-encryption.md)

- [Microsoft Purview の高度なメッセージの暗号化を使って暗号化されたメールを取り消す](revoke-ome-encrypted-mail.md)

- [メッセージ ポリシーとコンプライアンス サービスの説明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
