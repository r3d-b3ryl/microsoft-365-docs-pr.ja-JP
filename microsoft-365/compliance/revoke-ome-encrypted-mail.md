---
title: Advanced Message Encryption によって暗号化された電子メールを取り消す
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 管理者として、またメッセージ送信者として、365 Advanced Message Encryption で暗号化された特定のメールOffice取り消しできます。
ms.openlocfilehash: 67582917dd483f6090f5cd369af8faf6cf8a4ea8
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105142"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Advanced Message Encryption によって暗号化された電子メールを取り消す

電子メールの取り消しは、Office 365 Advanced Message Encryption の一部として提供されます。 Office 365 Advanced Message Encryption は [、Microsoft 365 Enterprise E5、Office](https://www.microsoft.com/microsoft-365/enterprise/home)365 E5、Microsoft 365 E5 (Nonprofit Staff Pricing)、Office 365 Enterprise E5 (Nonprofit Staff Pricing)、および Office 365 Education A5 に含まれています。 組織に 365 Advanced Message Encryption Office含めないサブスクリプションがある場合、 Microsoft 365 E3 用の Microsoft 365 E5 コンプライアンス SKU アドオン、Microsoft 365 E3 (Nonprofit Staff Pricing)、または microsoft 365 E3、Microsoft 365 E3 (Nonprofit Staff Pricing)、または Office 365 Advanced Compliance SKU アドオン、または Office 365 SKU で購入できます。

この記事は、Office [365 Message Encryption](ome.md)に関する大規模な一連の記事の一部です。

Office 365 Advanced Message Encryption を使用してメッセージが暗号化され、Microsoft 365 管理者またはメッセージの送信者である場合は、特定の条件下でメッセージを取り消す可能性があります。 管理者は PowerShell を使用してメッセージを取り消します。 送信者は、Outlook on the web から直接送信したメッセージを取り消します。 この記事では、失効が可能な状況と取り消し方法について説明します。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>取り消し可能な暗号化されたメール

管理者とメッセージ送信者は、受信者がリンクベースのブランド化された暗号化された電子メールを受信した場合、暗号化された電子メールを取り消す可能性があります。 受信者がサポートされている Outlook クライアントでネイティブインライン エクスペリエンスを受信した場合、メッセージを取り消すことはできません。

受信者がリンク ベースのエクスペリエンスとインライン エクスペリエンスのどちらのエクスペリエンスを受け取るかどうかは、受信者 ID の種類によって異なります。Office 365 と Microsoft アカウントの受信者 (outlook.com ユーザーなど) は、サポートされている Outlook クライアントでインライン エクスペリエンスを受け取ります。 Gmail や Yahoo の受信者など、他のすべての受信者の種類には、リンク ベースのエクスペリエンスが提供されます。

管理者とメッセージ送信者は、Outlook on the web から直接適用された暗号化を使用して暗号化されたメッセージを取り消す可能性があります。 たとえば、[暗号化のみ] オプションを使用して暗号化されたメッセージなどです。

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Outlook on the web の [暗号化のみ] オプションを示すスクリーンショット。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>失効した暗号化されたメールの受信者エクスペリエンス

電子メールが失効すると、受信者は Office 365 Message Encryption ポータルを通じて暗号化された電子メールにアクセスすると、「メッセージは送信者によって取り消されました」というエラーを受け取ります。

![失効した暗号化された電子メールを示すスクリーンショット。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>送信した暗号化されたメッセージを取り消す方法

1 人の受信者に送信したメールを取り消し、その受信者がソーシャル アカウント (gmail.com や yahoo.com など) を使用yahoo.com。 つまり、リンク ベースのエクスペリエンスを受け取った 1 人の受信者に送信された電子メールを取り消す可能性があります。

Office 365 または Microsoft 365 の仕事または学校のアカウントを使用する受信者、または microsoft アカウントを使用するユーザー (outlook.com アカウントなど) に送信したメールを取り消しすることはできません。 

送信した暗号化されたメッセージを取り消す場合は、次の手順を実行します。

1. Outlook on the web の **送信** フォルダーで、取り消すメッセージを参照します。

   メールが取り消し可能な場合は、メッセージの上部に [外部アクセスの削除] リンクが表示されます。

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Outlook on the web で取り消す暗号化されたメールを示すスクリーンショット。":::

2. [外部 **アクセスの削除] をクリック** してメッセージを取り消します。

   メッセージは、その状態が取り消された状態を示しています。

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Outlook on the web で取り消された暗号化されたメッセージを示すスクリーンショット。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>管理者として暗号化されたメッセージを取り消す方法

Microsoft 365 管理者は、次の一般的な手順に従って、有効な暗号化された電子メールを取り消します。

- 電子メールのメッセージ ID を取得します。
- メッセージを取り消し可能な場合を確認します。
- メールを取り消します。

### <a name="step-1-obtain-the-message-id-of-the-email"></a>手順 1. 電子メールのメッセージ ID を取得する

暗号化されたメールを取り消す前に、メールのメッセージ ID を収集します。 通常、MessageId の形式は次の形式です。

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

取り消す電子メールのメッセージ ID を検索する方法は複数あります。 このセクションでは、いくつかのオプションについて説明しますが、ID を提供する任意のメソッドを使用できます。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>セキュリティ コンプライアンス センターでメッセージ追跡を使用して、取り消す電子メールのメッセージ ID を &amp; 識別するには

1. セキュリティ/コンプライアンス センターで新しいメッセージ追跡を使用して、送信者または受信者& [検索します](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)。

2. メールを見つから選択すると、[メッセージ追跡の詳細] ウィンドウ **が表示** されます。 [ **詳細] を展開** してメッセージ ID を見つける。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>セキュリティ コンプライアンス センターのメッセージ暗号化レポートを使用してOfficeのメッセージ ID を &amp; 特定するには

1. セキュリティ コンプライアンス センター &amp; で、メッセージ暗号化レポート **に移動します**。 このレポートの詳細については、セキュリティ コンプライアンス センター [でメール セキュリティ レポートを表示するを &amp; 参照してください](../security/office-365-security/view-email-security-reports.md)。

2. [詳細 **の表示] テーブル** を選択し、取り消すメッセージを特定します。

3. メッセージ ID を含む詳細を表示するには、メッセージをダブルクリックします。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>手順 2. メールが取り消し可能な場合の確認

メッセージを取り消すかどうかを確認するには、セキュリティ コンプライアンス センターの [詳細] テーブルで、失効状態フィールドが暗号化レポートに表示されているかどうかを &amp; 確認します。

メール メッセージを使用して特定の電子メール メッセージを取り消Windows PowerShell、次の手順を実行します。

1. 組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. 次のようにGet-OMEMessageStatusコマンドレットを実行します。

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   このコマンドは、メッセージの件名と、メッセージが取り消し可能かどうかを返します。 例えば、

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>手順 3. メールを取り消す

取り消す電子メールのメッセージ ID を確認し、メッセージが取り消し可能なと確認したら、セキュリティ コンプライアンス センターまたは Windows PowerShell を使用して電子メールを取り消 &amp; します。

セキュリティ コンプライアンス センターを使用してメッセージを &amp; 取り消す方法

1. 組織のグローバル管理者のアクセス許可を持つ、仕事または学校のアカウントを使用して、セキュリティ/コンプライアンス センター&接続します。

2. 暗号化レポート **のメッセージの** 詳細テーブル **で** 、[メッセージの取り消し **] を選択します**。

電子メール を使用して電子メールを取りWindows PowerShell、次のコマンドレットSet-OMEMessageRevocationします。

1. 組織でグローバル管理者のアクセス許可を持つ、仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](https://aka.ms/exopowershell)。

2. 次のようにSet-OMEMessageRevocationコマンドレットを実行します。

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 電子メールが取り消されたかどうかを確認するには、次Get-OMEMessageStatusコマンドレットを実行します。

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    失効が成功した場合、コマンドレットは次の結果を返します。  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>365 Advanced Message Encryption Officeの詳細

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Office 365 Advanced Message Encryption - 電子メールの有効期限](ome-advanced-expiration.md)

- [メッセージ ポリシーとコンプライアンス サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
