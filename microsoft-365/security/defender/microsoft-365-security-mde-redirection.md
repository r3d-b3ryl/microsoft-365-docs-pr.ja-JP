---
title: Microsoft Defender for Endpoint からアカウントをユーザーにリダイレクトMicrosoft 365 Defender
description: Defender for Endpoint からアカウントとセッションをユーザーにリダイレクトするMicrosoft 365 Defender。
keywords: Microsoft 365 Defender、 セキュリティ センターのリダイレクトMicrosoft 365 Defenderを開始する
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
ms.openlocfilehash: c92788d13292501076e98e3cafeb2d145835de4d5ddde6b7822e79bc58680a7b
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53838729"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a>Microsoft Defender for Endpoint からアカウントをユーザーにリダイレクトMicrosoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender
- Defender for Endpoint

SIEM と拡張検出と応答 (XDR) による脅威保護に対する Microsoft のクロスドメインアプローチに合わせ、Microsoft Defender Advanced Threat Protection を Microsoft Defender for Endpoint として再ブランド化し、それを単一の統合ポータル Microsoft 365 Defender に統合しました。

このガイドでは、以前の Microsoft Defender for Endpoint ポータル (securitycenter.windows.com または securitycenter.microsoft.com) から Microsoft 365 Defender ポータル (security.microsoft.com) への自動リダイレクトを有効にすることで、アカウントを Microsoft 365 Defender にルーティングする方法について説明します。

> [!NOTE]
> microsoft Defender for Endpoint in Microsoft 365 Defender では[、Microsoft Defender](./mssp-access.md)セキュリティ センターでのアクセス許可と同じ方法で、マネージド セキュリティ サービス プロバイダー [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)へのアクセス許可をサポートしています。

## <a name="what-to-expect"></a>想定される変化
自動リダイレクトを有効にすると、securitycenter.windows.com または securitycenter.microsoft.com の元 Microsoft Defender for Endpoint ポータルにアクセスするアカウントが、security.microsoft.com の Microsoft 365 Defender ポータルに自動的にルーティングされます。
 
変更点の詳細については[、「Microsoft Defender for Endpoint in Microsoft 365 Defender」を参照してください](microsoft-365-security-center-mde.md)。

これには、以前の securitycenter.windows.com ポータルを指すリンク (電子メール通知のリンクなど) や SIEM API 呼び出しによって返されるリンクなど、ブラウザー経由で以前のポータルに直接アクセスするリダイレクトが含まれます。  

 メール通知または SIEM API からの外部リンクには、現在、両方のポータルへのリンクが含まれている。 リダイレクトが有効になると、両方のリンクは、古いMicrosoft 365 Defender削除されるまで、そのリンクをポイントします。 新しいリンクを使用して、新しいリンクを参照Microsoft 365 Defender。

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
有効にすると、この更新プログラムは一部のアカウントでほぼ直ちに有効になる可能性があります。 ただし、リダイレクトが組織内のすべてのアカウントに伝達されるのに時間がかかる場合があります。 この設定が適用されている間、アクティブなセッションのアカウントはセッションから取り出され、現在のセッションを終了して再びサインインした後にのみ Microsoft 365 Defender にルーティングされます。  

### <a name="set-up-portal-redirection"></a>ポータルリダイレクトの設定
アカウントのルーティングを開始するには、次Microsoft 365 Defender。
1. Azure Active directory でグローバル管理者またはセキュリティ管理者のアクセス許可を持っている必要があります。 

2. [サインインして](https://security.microsoft.com/)、Microsoft 365 Defender。

3. [エンドポイントの **全般設定**  >  **リダイレクト**  >  **] に**  >  **移動するか、** ここを [クリックします](https://security.microsoft.com/preferences2/portal_redirection)。  

4. [自動リダイレクト] 設定を [オン] に **切り替える**。

5. [有効 **にする]** をクリックして、自動リダイレクトをMicrosoft 365 Defender。

>[!IMPORTANT]
>この設定を有効にすると、アクティブなユーザー セッションは終了しません。 この設定が適用されている間にアクティブ なセッションに参加しているアカウントは、現在のセッションを終了Microsoft 365 Defenderサインインした後にのみ、ユーザーに指示されます。

>[!NOTE]
>この設定を有効または無効にするには、グローバル管理者またはセキュリティ管理者Azure Active Directoryアクセス許可を持っている必要があります。  

## <a name="can-i-go-back-to-using-the-former-portal"></a>以前のポータルを使用して戻ってみませんか?
何かが機能していない場合、またはユーザーが作業を完了できないMicrosoft 365 Defender、そのことを聞きたいと思います。 リダイレクトに関する問題が発生した場合は、[フィードバックの送信] フォームを使用してお知らせください。

元の Microsoft Defender for Endpoint ポータルに戻すには、次の操作を行います。

1. [グローバル管理者](https://security.microsoft.com/)としてMicrosoft 365 Defenderサインインするか、Azure Active directory でセキュリティ管理者のアクセス許可を持つアカウントを使用します。

2. [エンドポイント全般 **設定**  >  **リダイレクト] に**  >    >  **移動するか、**[ここでページを開きます](https://security.microsoft.com/preferences2/portal_redirection)。  

3. [自動リダイレクト] 設定を [オフ] に **切り替えます**。

4. メッセージが **表示されたら** 、[&フィードバックを共有する] をクリックします。

この設定は、いつでも再度有効にできます。 

無効にすると、アカウントは security.microsoft.com にルーティングされ、以前のポータル (securitycenter.windows.com または securitycenter.microsoft.com) に再びアクセスできます。 

## <a name="related-information"></a>関連情報
- [Microsoft 365 Defender概要](overview-security-center.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft は、セキュリティ操作を最新化するために統合された SIEM と XDR を提供します。](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR と SIEM のインフォグラフィック](https://afrait.com/blog/xdr-versus-siem/) 
- [新しい Defender](https://afrait.com/blog/the-new-defender/) 
- [概要 Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft セキュリティ ポータルと管理センター](portals.md)