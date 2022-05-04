---
title: 高度なメッセージ暗号化によって暗号化された電子メールを取り消す
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 05/02/2022
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 管理者およびメッセージ送信者として、Microsoft Purview Advanced Message Encryption で暗号化された特定のメールを取り消すことができます。
ms.openlocfilehash: 79d09c13755c0c73e4d68598e83ac41344b9281a
ms.sourcegitcommit: 7e0094ddff54bcbe5d691dba58d4c4fb86f8b1a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2022
ms.locfileid: "65187945"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>高度なメッセージ暗号化によって暗号化された電子メールを取り消す

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

電子メール失効は、Microsoft Purview Advanced Message Encryption の一部として提供されます。 Microsoft Purview Advanced Message Encryption は[、Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非営利団体スタッフ価格)、Office 365 Enterprise E5 (非営利団体スタッフ価格)、およびOffice 365 Education A5。 Advanced Message Encryption の失効と有効期限の機能を使用するには、E5 ライセンス **の Office 365 オプションでプレミアム暗号化** を有効にします。

組織に Microsoft Purview Advanced Message Encryption を含まないサブスクリプションがある場合は、Microsoft 365 E3、Microsoft 365 E3 (非営利団体スタッフ価格)、またはMicrosoft 365 E5 Compliance SKU アドオンで購入できます。Microsoft 365 E3、Microsoft 365 E3 (非営利団体スタッフの価格)、またはOffice 365 SKU 用の SKU アドオンをOffice 365 Advanced Complianceします。

この記事は、[Office 365 メッセージ](ome.md)暗号化に関する大規模な一連の記事の一部です。

Microsoft Purview Advanced Message Encryption を使用してメッセージが暗号化され、Microsoft 365管理者であるか、メッセージの送信者である場合は、特定の条件下でメッセージを取り消すことができます。 管理者は PowerShell を使用してメッセージを取り消します。 送信者は、Outlook on the webから直接送信したメッセージを取り消します。 この記事では、失効が可能な状況とその方法について説明します。

> [!NOTE]
> OME メッセージを追跡および取り消すことができることを保証するには、カスタム ブランド テンプレートを追加する必要があります。 [暗号化されたメッセージに組織のブランドを追加するを](add-your-organization-brand-to-encrypted-messages.md)参照してください
  
## <a name="encrypted-emails-that-you-can-revoke"></a>取り消すことができる暗号化された電子メール

受信者がリンクベースのブランド化された暗号化された電子メールを受信した場合、管理者とメッセージの送信者は暗号化されたメールを取り消すことができます。 受信者がサポートされているOutlook クライアントでネイティブ インライン エクスペリエンスを受け取った場合、メッセージを取り消すことはできません。

受信者がリンクベースのエクスペリエンスを受け取るか、インライン エクスペリエンスを受け取るかは、受信者 ID の種類によって異なります。Office 365と Microsoft アカウントの受信者 (outlook.com ユーザーなど) は、サポートされているOutlook クライアントでインライン エクスペリエンスを取得します。 Gmail や Yahoo の受信者など、他のすべての受信者の種類では、リンクベースのエクスペリエンスが得られます。

管理者とメッセージの送信者は、Outlook on the webから直接適用された暗号化を使用して暗号化されたメッセージを取り消すことができます。 たとえば、[暗号化のみ] オプションを使用して暗号化されたメッセージなどです。

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Outlook on the webの [暗号化のみ] オプションを示すスクリーンショット。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>取り消された暗号化された電子メールの受信者エクスペリエンス

電子メールが取り消されると、受信者はOffice 365メッセージ暗号化ポータルから暗号化された電子メールにアクセスするときにエラーを受け取ります。"メッセージは送信者によって取り消されました"。

![取り消された暗号化された電子メールを示すスクリーンショット。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>送信した暗号化されたメッセージを取り消す方法

gmail.com や yahoo.com などのソーシャル アカウントを使用する 1 人の受信者に送信したメールを取り消すことができます。 つまり、リンク ベースのエクスペリエンスを受け取った 1 人の受信者に送信された電子メールを取り消すことができます。

職場または学校のアカウントを使用する受信者に送信したメールを、Office 365、Microsoft 365、または Microsoft アカウントを使用するユーザー (outlook.com アカウントなど) から取り消すことはできません。 

送信した暗号化されたメッセージを取り消すには、次の手順を実行します。

1. Outlook on the webの **[送信済み]** フォルダーで、取り消すメッセージを参照します。

   メールが取り消し可能な場合は、メッセージの上部に [外部アクセスの削除] リンクが表示されます。

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Outlook on the webで取り消す暗号化されたメールを示すスクリーンショット。":::

2. [ **外部アクセスの削除]** をクリックしてメッセージを取り消します。

   メッセージは、その状態が取り消されたことを示します。

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Outlook on the webで取り消された暗号化されたメッセージを示すスクリーンショット。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>管理者として暗号化されたメッセージを取り消す方法

Microsoft 365管理者は、次の一般的な手順に従って、対象となる暗号化されたメールを取り消します。

- 電子メールのメッセージ ID を取得します。
- メッセージを取り消すことができることを確認します。
- メールを取り消します。

### <a name="step-1-obtain-the-message-id-of-the-email"></a>手順 1. 電子メールのメッセージ ID を取得する

暗号化されたメールを取り消す前に、メールのメッセージ ID を収集します。 MessageId は通常、次の形式です。

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

取り消すメールのメッセージ ID を見つける方法は複数あります。 このセクションではいくつかのオプションについて説明しますが、ID を提供する任意のメソッドを使用できます。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>セキュリティ &amp; コンプライアンス センターのメッセージ トレースを使用して取り消す電子メールのメッセージ ID を識別するには

1. [セキュリティ & コンプライアンス センターの新しいメッセージ トレース](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)を使用して、送信者または受信者別に電子メールを検索します。

2. メールが見つかったら、それを選択して [ **メッセージ トレースの詳細** ] ウィンドウを表示します。 **[詳細情報]** を展開して、メッセージ ID を見つけます。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-encryption-reports-in-the-security-amp-compliance-center"></a>セキュリティ &amp; コンプライアンス センターのメッセージ暗号化レポートを使用して取り消す電子メールのメッセージ ID を識別するには

1. セキュリティ &amp; コンプライアンス センターで、 **メッセージ暗号化レポート** に移動します。 このレポートの詳細については、「 [セキュリティ &amp; コンプライアンス センターで電子メール セキュリティ レポートを表示する](../security/office-365-security/view-email-security-reports.md)」を参照してください。

2. [ **詳細の表示** ] テーブルを選択し、取り消すメッセージを特定します。

3. メッセージをダブルクリックすると、メッセージ ID を含む詳細が表示されます。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>手順 2。 メールが取り消し可能であることを確認する

メッセージを取り消すことができるかどうかを確認するには、セキュリティ &amp; コンプライアンス センターの **[詳細**] テーブルの [暗号化] レポートに [失効状態] フィールドが表示されているかどうかを確認します。

Windows PowerShellを使用して特定の電子メール メッセージを取り消すことができるかどうかを確認するには、次の手順を実行します。

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用して、Windows PowerShell セッションを開始し、Exchange Onlineに接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. 次のようにGet-OMEMessageStatusコマンドレットを実行します。

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   このコマンドは、メッセージの件名と、メッセージが取り消し可能かどうかを返します。 例えば、

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>手順 3. メールを取り消す

取り消すメールのメッセージ ID がわかり、メッセージが取り消し可能であることを確認したら、セキュリティ &amp; コンプライアンス センターまたはWindows PowerShellを使用して電子メールを取り消すことができます。

セキュリティ &amp; コンプライアンス センターを使用してメッセージを取り消すには

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用して、セキュリティ & コンプライアンス センターに接続します。

2. **暗号化レポート** のメッセージの **[詳細**] テーブルで、[メッセージの **取り消し]** を選択します。

Windows PowerShellを使用して電子メールを取り消すには、Set-OMEMessageRevocation コマンドレットを使用します。

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用[して、PowerShell をExchange Online Connect](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 次のようにSet-OMEMessageRevocationコマンドレットを実行します。

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 電子メールが取り消されたかどうかを確認するには、次のようにGet-OMEMessageStatusコマンドレットを実行します。

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    失効が成功した場合、コマンドレットは次の結果を返します。  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-microsoft-purview-advanced-message-encryption"></a>Microsoft Purview Advanced Message Encryption の詳細

- [Microsoft Purview Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Microsoft Purview Advanced Message Encryption - 電子メールの有効期限](ome-advanced-expiration.md)

- [メッセージ ポリシーとコンプライアンス サービスの説明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
