---
title: Microsoft Defender for Endpoint から Microsoft Defender へのアカウントのリダイレクトMicrosoft 365 Defender
description: アカウントとセッションを Defender for Endpoint から Defender にリダイレクトするMicrosoft 365方法。
keywords: Microsoft 365Defender、 Defender の使用Microsoft 365、セキュリティ センターのリダイレクト
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
ms.openlocfilehash: c678cb8d9eece9ff3a900a7d2b0c6bf95ad8eda9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842568"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>Microsoft Defender for Endpoint から Microsoft Defender へのアカウントのリダイレクトMicrosoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender
- Defender for Endpoint

SIEM と拡張検出と応答 (XDR) による脅威保護に対する Microsoft のクロスドメインアプローチに合わせ、Microsoft Defender Advanced Threat Protection を Microsoft Defender for Endpoint として再ブランド化し、それを単一の統合ポータル Microsoft 365 Defender に統合しました。

このガイドでは、元の Microsoft Defender for Endpoint ポータル (securitycenter.windows.com または securitycenter.microsoft.com) から Microsoft 365 Defender ポータル (security.microsoft.com) への自動リダイレクトを有効にすることで、アカウントを Microsoft 365 Defender にルーティングする方法について説明します。

> [!NOTE]
> Microsoft Defender for Endpoint in Microsoft 365 Defender は[、Microsoft Defender](./mssp-access.md)セキュリティ センターでアクセスを許可するのと同じ方法で、マネージド セキュリティ サービス プロバイダー [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)へのアクセス許可をサポートしています。

## <a name="what-to-expect"></a>想定される変化
自動リダイレクトが有効になると、securitycenter.windows.com または securitycenter.microsoft.com の元の Microsoft Defender for Endpoint ポータルにアクセスするアカウントは、security.microsoft.com の Microsoft 365 Defender ポータルに自動的にルーティングされます。
 
変更点について詳しくは[、「Microsoft Defender for Endpoint in Microsoft 365」をご覧ください](microsoft-365-security-center-mde.md)。

これには、以前の securitycenter.windows.com ポータルを指すリンク (電子メール通知のリンクなど) や SIEM API 呼び出しによって返されるリンクなど、ブラウザー経由で以前のポータルに直接アクセスするリダイレクトが含まれます。  

 メール通知または SIEM API からの外部リンクには、現在、両方のポータルへのリンクが含まれている。 リダイレクトが有効になると、両方のリンクは、Microsoft 365が削除されるまで Defender を指します。 Defender を指す新しいリンクを採用Microsoft 365勧めします。

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
有効にすると、この更新プログラムは一部のアカウントでほぼ直ちに有効になる可能性があります。 ただし、リダイレクトが組織内のすべてのアカウントに伝達されるのに時間がかかる場合があります。 この設定が適用されている間、アクティブなセッションのアカウントはセッションから取り出されません。現在のセッションを終了して再びサインインした後、Microsoft 365 Defender にのみルーティングされます。  

### <a name="set-up-portal-redirection"></a>ポータルリダイレクトの設定
Defender へのアカウントのルーティングをMicrosoft 365するには、次の手順を実行します。
1. Azure Active directory でグローバル管理者またはセキュリティ管理者のアクセス許可を持っている必要があります。 

2. [Defender に](https://security.microsoft.com/)サインインMicrosoft 365します。

3. [エンドポイントの **全般設定**  >  **リダイレクト**  >  **] に**  >  **移動するか、** ここを [クリックします](https://security.microsoft.com/preferences2/portal_redirection)。  

4. [自動リダイレクト] 設定を [オン] に **切り替える**。

5. [有効 **にする] を** クリックして、Defender に自動リダイレクトMicrosoft 365適用します。

>[!IMPORTANT]
>この設定を有効にすると、アクティブなユーザー セッションは終了しません。 この設定が適用されている間にアクティブ なセッションに参加しているアカウントは、現在のセッションを終了し、もう一度サインインした後Microsoft 365 Defender に移動されます。

>[!NOTE]
>この設定を有効または無効にするには、グローバル管理者またはセキュリティ管理者Azure Active Directoryアクセス許可を持っている必要があります。  

## <a name="can-i-go-back-to-using-the-former-portal"></a>以前のポータルを使用して戻ってみませんか?
何かが機能していない場合や、Microsoft 365 Defender を通じて完了できない場合は、そのことをお知りください。 リダイレクトに関する問題が発生した場合は、[フィードバックの送信] フォームを使用してお知らせください。

元の Microsoft Defender for Endpoint ポータルに戻すには、次の操作を行います。

1. [グローバル管理者](https://security.microsoft.com/)としてMicrosoft 365 Defender にサインインするか、Azure Active directory でセキュリティ管理者のアクセス許可を持つアカウントを使用します。

2. [エンドポイント全般 **設定**  >  **リダイレクト] に**  >    >  **移動するか、**[ここでページを開きます](https://security.microsoft.com/preferences2/portal_redirection)。  

3. [自動リダイレクト] 設定を [オフ] に **切り替えます**。

4. メッセージが **表示されたら** 、[&フィードバックを共有する] をクリックします。

この設定は、いつでも再度有効にできます。 

無効にすると、アカウントは security.microsoft.com にルーティングされ、以前のポータル (securitycenter.windows.com または securitycenter.microsoft.com) に再びアクセスできます。 

## <a name="related-information"></a>関連情報
- [Microsoft 365Defender の概要](overview-security-center.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft は、セキュリティ操作を最新化するために統合された SIEM と XDR を提供します。](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR と SIEM のインフォグラフィック](https://afrait.com/blog/xdr-versus-siem/) 
- [新しい Defender](https://afrait.com/blog/the-new-defender/) 
- [Defender Microsoft 365について](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft セキュリティ ポータルと管理センター](portals.md)