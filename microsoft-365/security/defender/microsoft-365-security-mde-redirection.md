---
title: Microsoft Defender for EndpointからMicrosoft 365 Defenderへのアカウントのリダイレクト
description: Defender for Endpoint から Microsoft 365 Defenderにアカウントとセッションをリダイレクトする方法。
keywords: Microsoft 365 Defender、Microsoft 365 Defenderの概要、セキュリティ センターのリダイレクト
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.openlocfilehash: 90ddf53090f79c3d372aa2119330e71919849bc0
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479976"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>Microsoft Defender for EndpointからMicrosoft 365 Defenderへのアカウントのリダイレクト

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender
- Defender for Endpoint

SIEM と拡張検出と応答 (XDR) を使用した脅威保護に対する Microsoft のクロスドメイン アプローチと連携して、Microsoft Defender Advanced Threat Protection のブランドをMicrosoft Defender for Endpointとして再ブランド化し、Microsoft 365 Defenderという 1 つの統合ポータルに統合しました。

このガイドでは、以前のMicrosoft Defender for Endpoint ポータル (securitycenter.windows.com または securitycenter.microsoft.com) からMicrosoft 365 Defenderへの自動リダイレクトを有効にして、アカウントを<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>にルーティングする方法について説明します。

> [!NOTE]
> Microsoft 365 DefenderのMicrosoft Defender for Endpointでは、Microsoft Defender セキュリティ センターでアクセスが許可されるのと同じ方法で[マネージド セキュリティ サービス プロバイダー (MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) へのアクセス[を許可](./mssp-access.md)できます。

## <a name="what-to-expect"></a>想定される変化

自動リダイレクトが有効になると、securitycenter.windows.com または securitycenter.microsoft.com で以前のMicrosoft Defender for Endpoint ポータルにアクセスするアカウントは、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><security.microsoft.com></a>のMicrosoft 365 Defender ポータルに自動的にルーティングされます。

変更点の詳細については、[Microsoft 365 DefenderのMicrosoft Defender for Endpoint](microsoft-365-security-center-mde.md)を参照してください。

これには、メール通知のリンクや SIEM API 呼び出しによって返されるリンクなど、以前の securitycenter.windows.com ポータルを指すリンクなど、ブラウザー経由で元のポータルに直接アクセスするためのリダイレクトが含まれます。  

 メール通知または SIEM API からの外部リンクには、現在、両方のポータルへのリンクが含まれています。 リダイレクトが有効になると、古いリンクが最終的に削除されるまで、両方のリンクがMicrosoft 365 Defenderをポイントします。 Microsoft 365 Defenderを指す新しいリンクを採用することをお勧めします。

リンクとルーティングの詳細については、次の表を参照してください。
## <a name="siem-api-routing"></a>SIEM API ルーティング

| プロパティ | リダイレクトが OFF の場合の宛先 | リダイレクトが ON の場合の宛先 |
|---------|---------|---------|
| LinkToWDATP | securitycenter.windows.com の [アラート] ページ | security.microsoft.com の [アラート] ページ |
| IncidentLinkToWDATP | securitycenter.windows.com の [インシデント] ページ | security.microsoft.com の [インシデント] ページ |
| LinkToMTP | security.microsoft.com の [アラート] ページ | security.microsoft.com の [アラート] ページ |
| IncidentLinkToMTP | security.microsoft.com の [インシデント] ページ | security.microsoft.com の [インシデント] ページ |

## <a name="email-alert-notifications"></a>アラート通知をEmailする

| プロパティ | リダイレクトが OFF の場合の宛先** | リダイレクトが ON の場合の宛先 |
|---------|---------|---------|
| [アラート] ページ | securitycenter.windows.com の [アラート] ページ | security.microsoft.com の [アラート] ページ |
| [インシデント] ページ |securitycenter.windows.com の [インシデント] ページ | security.microsoft.com の [インシデント] ページ |
| Defender for Cloud ポータルの [アラート] ページ | security.microsoft.com の [アラート] ページ | security.microsoft.com の [アラート] ページ |
| Defender for Cloud portal の [インシデント] ページ | security.microsoft.com の [インシデント] ページ | security.microsoft.com の [インシデント] ページ |

## <a name="when-does-this-take-effect"></a>これはいつ有効になりますか?

有効にすると、この更新プログラムは、一部のアカウントでほぼすぐに有効になる可能性があります。 ただし、リダイレクトが組織内のすべてのアカウントに伝達されるまでに時間がかかる場合があります。 この設定が適用されている間、アクティブセッションのアカウントはセッションから取り出されず、現在のセッションを終了してもう一度サインインした後にのみMicrosoft 365 Defenderにルーティングされます。  

### <a name="set-up-portal-redirection"></a>ポータル リダイレクトを設定する

Microsoft 365 Defenderへのアカウントのルーティングを開始するには:

1. グローバル管理者であるか、Azure Active Directory のセキュリティ管理者のアクセス許可があることを確認します。

2. Microsoft 365 Defenderにサインイン<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">します</a>。

3. **[Settings** > **Endpoints** > **General** > **Portal] リダイレクト** に移動するか [、ここをクリックします](https://security.microsoft.com/preferences2/portal_redirection)。  

4. [自動リダイレクト] 設定を **[オン]** に切り替えます。

5. **[有効] を** クリックして、Microsoft 365 Defenderに自動リダイレクトを適用します。

>[!IMPORTANT]
>この設定を有効にした場合、アクティブなユーザー セッションは終了しません。 この設定が適用されている間にアクティブなセッションに参加しているアカウントは、現在のセッションを終了してもう一度サインインした後にのみMicrosoft 365 Defenderに送信されます。

>[!NOTE]
>この設定を有効または無効にするには、グローバル管理者であるか、Azure Active Directory のセキュリティ管理者のアクセス許可が必要です。  

## <a name="can-i-go-back-to-using-the-former-portal"></a>以前のポータルの使用に戻ることはできますか?

何かがうまくいっていない場合、またはMicrosoft 365 Defenderを通じて完了できない場合は、そのことについてお聞かせたい場合があります。 リダイレクトに関する問題が発生した場合は、フィードバックの送信フォームを使用してお知らせください。

以前のMicrosoft Defender for Endpoint ポータルに戻すには:

1. グローバル管理者として<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>にサインインするか、Azure Active directory でセキュリティ管理者のアクセス許可を使用してアカウントを使用します。

2. **[Settings** > **Endpoints** > **General** > **Portal] リダイレクト** に移動するか [、ここでページを開きます](https://security.microsoft.com/preferences2/portal_redirection)。  

3. [自動リダイレクト] 設定を **[オフ]** に切り替えます。

4. メッセージが表示されたら、[フィードバックの共有& **無効にする]** をクリックします。

この設定は、いつでも再度有効にすることができます。 

無効にすると、アカウントは security.microsoft.com にルーティングされなくなり、以前のポータル (securitycenter.windows.com または securitycenter.microsoft.com) にもう一度アクセスできるようになります。 

## <a name="related-information"></a>関連情報
- [Microsoft 365 Defenderの概要](microsoft-365-defender.md)
- [Microsoft 365 Defender の Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [Microsoft は、セキュリティ操作を最新化するために、統合された SIEM と XDR を提供します](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR と SIEM インフォグラフィック](https://afrait.com/blog/xdr-versus-siem/) 
- [`The New Defender`](https://afrait.com/blog/the-new-defender/) 
- [Microsoft 365 Defenderについて](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft セキュリティ ポータルと管理センター](portals.md)
