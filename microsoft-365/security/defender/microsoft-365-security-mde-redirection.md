---
title: アカウントを Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターにリダイレクトする
description: Defender for Endpoint からセキュリティ センターにアカウントとセッションMicrosoft 365する方法。
keywords: Microsoft 365センター, セキュリティ センターのMicrosoft 365開始, セキュリティ センターのリダイレクト
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: db458015d8434843ec64f3c2c00d640d4c4d8ff2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760178"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a>アカウントを Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターにリダイレクトする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender
- Defender for Endpoint

SIEM と拡張検出と応答 (XDR) による脅威保護に対する Microsoft のクロスドメインアプローチに合わせ、Microsoft Defender Advanced Threat Protection を Microsoft Defender for Endpoint として再ブランド化し、Microsoft 365 セキュリティ センターという単一の統合ポータルに統合しました。

このガイドでは、以前の Microsoft Defender for Endpoint ポータル (securitycenter.windows.com または securitycenter.microsoft.com) から Microsoft 365 セキュリティ センター ポータル (security.microsoft.com) への自動リダイレクトを有効にすることで、アカウントを Microsoft 365 セキュリティ センターにルーティングする方法について説明します。

> [!NOTE]
> Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint は、[Microsoft Defender セキュリティ センターでアクセスが許可される](./mssp-access.md)のと同じ方法で、[マネージド セキュリティ サービス プロバイダー (MSSP) へのアクセスの許可](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)をサポートします。

## <a name="what-to-expect"></a>想定される変化
自動リダイレクトが有効になると、securitycenter.windows.com または securitycenter.microsoft.com の元の Microsoft Defender for Endpoint ポータルにアクセスするアカウントが、security.microsoft.com の Microsoft 365 セキュリティ センター ポータルに自動的にルーティングされます。
 
変更点の詳細については[、「Microsoft Defender for Endpoint in the Microsoft 365」を参照してください](microsoft-365-security-center-mde.md)。

これには、以前の securitycenter.windows.com ポータルを指すリンク (電子メール通知のリンクなど) や SIEM API 呼び出しによって返されるリンクなど、ブラウザー経由で以前のポータルに直接アクセスするリダイレクトが含まれます。  

 メール通知または SIEM API からの外部リンクには、現在、両方のポータルへのリンクが含まれている。 リダイレクトが有効になると、両方のリンクは、Microsoft 365が削除されるまで、セキュリティ センターを指します。 セキュリティ センターを指す新しいリンクを採用Microsoft 365推奨します。

リンクとルーティングの詳細については、以下の表を参照してください。
## <a name="siem-api-routing"></a>SIEM API ルーティング

|**Property**  |**リダイレクトが OFF の場合の宛先**  |**リダイレクトが ON の場合の宛先** | 
|---------|---------|---------|
| LinkToWDATP | [アラート] ページ (securitycenter.windows.com | [アラート] ページ (security.microsoft.com  |
| IncidentLinkToWDATP | [インシデント] ページ (securitycenter.windows.com  | [インシデント] ページ (security.microsoft.com  |
| LinkToMTP | [アラート] ページ (security.microsoft.com | [アラート] ページ (security.microsoft.com  |
| IncidentLinkToMTP | [インシデント] ページ (security.microsoft.com  | [インシデント] ページ (security.microsoft.com  

## <a name="email-alert-notifications"></a>電子メールアラート通知

|**Property**  |**リダイレクトが OFF の場合の宛先**  |**リダイレクトが ON の場合の宛先** |
|---------|---------|---------|
| [アラート] ページ  | [アラート] ページ (securitycenter.windows.com  | [アラート] ページ (security.microsoft.com  |
| インシデント ページ  |[インシデント] ページ (securitycenter.windows.com  | [インシデント] ページ (security.microsoft.com  
| セキュリティ センター ポータルの [アラート] ページ | [アラート] ページ (security.microsoft.com | [アラート] ページ (security.microsoft.com | 
| セキュリティ センター ポータルのインシデント ページ | [インシデント] ページ (security.microsoft.com  | [インシデント] ページ (security.microsoft.com  |

## <a name="when-does-this-take-effect"></a>これはいつ有効になりますか? 
有効にすると、この更新プログラムは一部のアカウントでほぼ直ちに有効になる可能性があります。 ただし、リダイレクトが組織内のすべてのアカウントに伝達されるのに時間がかかる場合があります。 この設定が適用されている間、アクティブなセッションのアカウントはセッションから取り出され、現在のセッションを終了して再びサインインした後にのみ Microsoft 365 セキュリティ センターにルーティングされます。  

### <a name="set-up-portal-redirection"></a>ポータルリダイレクトの設定
アカウントをセキュリティ センターにルーティングMicrosoft 365するには、次の手順を実行します。
1. Azure Active directory でグローバル管理者またはセキュリティ管理者のアクセス許可を持っている必要があります。 

2. [セキュリティ センター](https://security.microsoft.com/)にサインインMicrosoft 365します。

3. [エンドポイントの **全般設定**  >  **リダイレクト**  >  **] に**  >  **移動するか、** ここを [クリックします](https://security.microsoft.com/preferences2/portal_redirection)。  

4. [自動リダイレクト] 設定を [オン] に **切り替える**。

5. [**有効にする]** をクリックして、セキュリティ センター ポータルMicrosoft 365リダイレクトを適用します。

>[!IMPORTANT]
>この設定を有効にすると、アクティブなユーザー セッションは終了しません。 この設定が適用されている間にアクティブなセッションに参加しているアカウントは、現在のセッションを終了して再度サインインした後Microsoft 365セキュリティ センターにのみ移動されます。

>[!NOTE]
>この設定を有効または無効にするには、グローバル管理者またはセキュリティ管理者Azure Active Directoryアクセス許可を持っている必要があります。  

## <a name="can-i-go-back-to-using-the-former-portal"></a>以前のポータルを使用して戻ってみませんか?
何かが機能していない場合や、Microsoft 365 セキュリティ センター ポータルで完了できないものがある場合は、そのことをお知りください。 リダイレクトに関する問題が発生した場合は、[フィードバックの送信] フォームを使用してお知らせください。

元の Microsoft Defender for Endpoint ポータルに戻すには、次の操作を行います。

1. [Azure](https://security.microsoft.com/) Active directory で、Microsoft 365管理者として、またはセキュリティ管理者のアクセス許可を持つアカウントを使用して、セキュリティ センターにサインインします。

2. [エンドポイント全般 **設定**  >  **リダイレクト] に**  >    >  **移動するか、**[ここでページを開きます](https://security.microsoft.com/preferences2/portal_redirection)。  

3. [自動リダイレクト] 設定を [オフ] に **切り替えます**。

4. メッセージが **表示されたら** 、[&フィードバックを共有する] をクリックします。

この設定は、いつでも再度有効にできます。 

無効にすると、アカウントは security.microsoft.com にルーティングされ、以前のポータル (securitycenter.windows.com または securitycenter.microsoft.com) に再びアクセスできます。 

## <a name="related-information"></a>関連情報
- [Microsoft 365 セキュリティ センターの概要](overview-security-center.md)
- [Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [Microsoft は、セキュリティ操作を最新化するために統合された SIEM と XDR を提供します。](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR と SIEM のインフォグラフィック](https://afrait.com/blog/xdr-versus-siem/) 
- [新しい Defender](https://afrait.com/blog/the-new-defender/) 
- [Defender Microsoft 365について](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft セキュリティ ポータルと管理センター](portals.md)