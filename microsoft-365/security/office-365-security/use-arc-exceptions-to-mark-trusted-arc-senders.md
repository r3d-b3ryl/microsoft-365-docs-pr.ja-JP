---
title: 送信側と受信側の間の正当なデバイスとサービスに Trusted ARC 送信者を使用する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: high
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 認証された受信チェーン (ARC) は、デバイス間の認証結果と、送信者と受信者の間で発生する間接的なメールフローを保持しようとする電子メール認証です。 信頼された ARC 送信者に対して例外を作成する方法を次に示します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c6845fd9137029ebebd031550e145aef8ffc1440
ms.sourcegitcommit: ec245c75006e3e5ed2b8e6c1b062fbb31a63aa6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2022
ms.locfileid: "67423721"
---
# <a name="make-a-list-of-trusted-arc-senders-to-trust-legitimate-indirect-mailflows"></a>*正当* な間接メールフローを信頼する信頼された ARC 送信者の一覧を作成する

**適用対象**

- Exchange Online Protection
- Microsoft Defender for Office 365 プラン 1 およびプラン 2
- Microsoft 365 Defender

[SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、[DKIM](use-dkim-to-validate-outbound-email.md)、[DMARC](use-dmarc-to-validate-email.md) などのEmail認証メカニズムは、電子メール受信者の *安全性* を確認するために使用されますが、正当なサービスによっては、送信者と受信者の間で電子メールが変更される場合があります。 **Microsoft 365 Defenderでは、ARC は、*正当な* 間接メールフローが原因で発生する SPF、DKIM、DMARC 配信エラーを減らすのに役立ちます。**

## <a name="authenticated-received-chain-arc-in-microsoft-365-defender-for-office"></a>Office のMicrosoft 365 Defenderで認証された受信チェーン (ARC)

組織への配信前に転送中のメッセージ コンテンツを変更するサービスは、DKIM 電子メール署名を無効にし、メッセージの認証に影響を与える可能性があります。 これらの中間サービスがこのようなアクションを実行すると、ARC を使用して、変更が発生する前に元の認証の詳細を提供できます。 その後、組織はこれらの詳細を信頼して、メッセージの認証に役立ちます。  

**信頼された ARC シールを使用すると、管理者は *信頼された* 中継局かの一覧をMicrosoft 365 Defender ポータルに追加できます。** 信頼された ARC シールを使用すると、Microsoft はこれらの信頼された中継局からの ARC 署名を受け入れ、これらの正当なメッセージが認証チェーンを失敗させるのを防ぎます。

> [!NOTE]
> ***信頼された ARC シールは、ARC シールを実装した中間ドメインの管理者が作成したリストです。*** 電子メールが Office 365 にルーティングされ、Office 365 テナントの ARC 信頼できる仲介者である場合、Microsoft は ARC 署名を検証し、ARC の結果に基づいて、指定された認証の詳細を受け入れることもできます。

## <a name="when-to-use-trusted-arc-sealers"></a>信頼できる ARC シールを使用するタイミング

信頼できる ARC シールの一覧は、仲介者が組織の電子メール フローの一部であり、次の場合にのみ必要です:

1. 電子メール ヘッダーまたは電子メールの内容を変更できます。
2. 他の理由 (添付ファイルの削除など) で認証が失敗する可能性があります。
 
信頼できる ARC シールを追加することで、Office 365 は、Office 365 でテナントにメールを配信するときに、シールラーが提供する認証結果を検証し、信頼します。

**管理者は、信頼された ARC シールとして *正当なサービスのみ* を追加する必要があります。** 組織が明示的に使用して認識するサービスのみを追加すると、最初にサービスを通過して電子メール認証チェックに合格し、認証エラーが原因で正当なメッセージが *迷惑* メールに送信されないようにする必要があるメッセージが役立ちます。

## <a name="steps-to-add-a-trusted-arc-sealer-to-microsoft-365-defender"></a>信頼された ARC シールをMicrosoft 365 Defenderに追加する手順

Microsoft 365 Defender ポータルの信頼された ARC シーラーには、テナントによって確認され、テナントに追加されたすべての ARC シールが表示されます。

**Microsoft 365 Defender ポータルで新しい信頼された ARC シールを追加するには:**

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ルール]** セクション \> **[ARC]** の **[メールとコラボレーション]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[メールの認証の設定]** に移動します。 ARC ページに直接移動するには、[メール認証設定](https://security.microsoft.com/authentication?viewid=ARC)を使用します。

2. 信頼できる ARC シールを初めて追加した場合は、[追加] ボタンをクリックします。
3. 表示されたテキスト ボックスに信頼できる ARC シールを追加します。
    1. ドメインを追加していることに注意してください (例: fabrikam.com)。
    1. ここで入力するドメイン名は、ARC-Seal および ARC-Message-Signature ヘッダーのドメイン 'd' タグに表示されるドメインと一致している *必要があります* (メッセージの電子メール ヘッダーに含まれます)。
    1. これらは、Outlook のメッセージのプロパティで確認できます。

## <a name="steps-to-validate-your-trusted-arc-sealer"></a>信頼された ARC シーラーを検証する手順

メッセージが Microsoft 365 Defender に到達する前にサード パーティからの ARC シールがある場合は、**電子メールが受信されたらヘッダーを確認し、最新の ARC ヘッダーを表示します**。

最後の ***ARC-Authentication-Results ヘッダー** _ で、ARC 検証が _*pass** として一覧表示されているかどうかを確認します。

1 の 'oda' を一覧表示する ARC ヘッダーは、以前の ARC が *検証され*、以前の ARC シールが *信頼* され、以前の *パス結果* を使用して現在の DMARC エラーをオーバーライドできることを示します。

**oda=1 を示す ARC パス ヘッダー**

oda の結果については、このヘッダー ブロックの最後にある電子メール認証方法を参照してください。

``
ARC-Authentication-Results: i=2; mx.microsoft.com 1; spf=pass (sender ip is
40.107.65.78) smtp.rcpttodomain=microsoft.com
smtp.mailfrom=sampledoamin.onmicrosoft.com; dmarc=bestguesspass action=none
header.from=sampledoamin.onmicrosoft.com; dkim=none (message not signed);
arc=pass (0 oda=1 ltdi=1
spf=[1,1,smtp.mailfrom=sampledoamin.onmicrosoft.com]
dkim=[1,1,header.d=sampledoamin.onmicrosoft.com]
dmarc=[1,1,header.from=sampledoamin.onmicrosoft.com])
``

DMARC エラーをオーバーライドするために ARC 結果が使用されたかどうかを確認するには、*compauth* 結果とヘッダーの *コードの理由 (130)* を探します。

*compauth* と *Reason* を見つけるには、このヘッダー ブロックの最後のエントリを参照してください。

``
Authentication-Results: spf=fail (sender IP is 51.163.158.241)
smtp.mailfrom=contoso.com; dkim=fail (body hash did not verify)
header.d=contoso.com;dmarc=fail action=none
header.from=contoso.com;compauth=pass reason=130
``

## <a name="powershell-steps-to-add-or-remove-a-trusted-arc-sealer"></a>信頼された ARC シーラーを追加または削除する PowerShell の手順

**管理者は、Exchange Online PowerShell を使用して ARC 構成を設定することもできます。**

1. Exchange Online PowerShell に接続します。
2. Connect-ExchangeOnline。
3. 信頼された ARC シーラーにドメインを追加または更新するには:
</br>
``
Set-ArcConfig -Identity default -ArcTrustedSealers {a list of arc signing domains split by comma}
``
</br>or</br>
``
Set-ArcConfig -Identity {tenant name/tenanid}\default -ArcTrustedSealers {a list of arc signing domains split by comma}
``
</br>*Set-ArcConfig* を実行するときは、ID パラメーター *-Identity* の既定値を指定する必要があります。 信頼されたシーラーは、 *ARC-Seal ヘッダー* の 'd' タグの値と一致する必要があります。

4. 信頼された ARC シールを表示します。
</br>
``
Get-ArcConfig
`` または ``
Get-ArcConfig - Organization {tenant name}
``

## <a name="trusted-arc-sealer-mailflow-graphics"></a>信頼された ARC シールのメールフロー グラフィックス

次の図は、SPF、DKIM、DMARC のいずれかの電子メール認証を使用する場合に、信頼できる ARC シールを使用する場合とない場合のメールフロー操作を比較したものです。 どちらのグラフィックスでも、メールフローに介入する必要がある正当なサービスが会社によって使用され、IP の送信と電子メール ヘッダーへの書き込みによって電子メール認証標準に違反する場合があります。 **最初のケースでは、管理者が信頼できる ARC シールを追加する *前に*、間接メールフロー トラフィックによって結果が示されます。**

:::image type="content" source="../../media/m365d-indirect-traffic-flow-without-trusted-arc-sealer.PNG" alt-text="この図では、Contoso は標準の電子メール セキュリティの一環として SPF、DKIM、DMARC を発行します。SPF を使用している送信者は、contoso.com 内から fabrikam.com にメールを送信し、このメールは Contoso が採用したサード パーティサービスを通過し、そのサービスは電子メール ヘッダーの送信 IP アドレスを変更します。EOP での DNS チェック中にサード パーティでコンテンツが変更されたため、IP と DKIM が変更されたため、メールは SPF に失敗します。SPF エラーと DKIM エラーのため、DMARC は失敗します。メッセージは迷惑メール、検疫、または拒否に送信されます。":::

ここでは、**信頼できる ARC シールを作成する機能を利用した後**、同じ組織が表示されます。

:::image type="content" source="../../media/m365d-indirect-traffic-flow-with-trusted-arc-sealer.PNG" alt-text="2 番目の図では、Contoso 社は信頼できる ARC シールの一覧を作成しました。同じユーザーが contoso.com から fabrikam.com に 2 番目のメールを送信します。Contoso によって採用されたサード パーティサービスは、メールのヘッダーにある送信者の IP アドレスを変更します。ただし、今回はサービスで ARC シールが実装されており、テナント管理者が信頼できる ARC シールにサード パーティのドメインを既に追加しているため、変更は受け入れられます。新しい IP アドレスに対して SPF が失敗します。DKIM は、コンテンツの変更のために失敗します。DMARC は、以前のエラーが原因で失敗します。ただし、ARC は変更を認識し、Pass を発行し、変更を受け入れます。スプーフィングはパスも受け取ります。メッセージが受信トレイに送信されます。":::

## <a name="next-steps-after-you-set-up-arc-for-microsoft-365-defender-for-office"></a>次の手順: Office 用に ARC for Microsoft 365 Defender を設定した後

セットアップ後、 [メッセージ ヘッダー アナライザー](https://mha.azurewebsites.net)を使用して ARC ヘッダーを確認します。

[SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、[DKIM](use-dkim-to-validate-outbound-email.md)、[DMARC](use-dmarc-to-validate-email.md)、構成手順を確認します。
