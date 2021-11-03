---
title: セキュリティとコンプライアンス センター Office 365から新しいアカウントにアカウントをリダイレクトMicrosoft 365 Defender
description: Defender for Office 365からMicrosoft 365 Defender。
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b2e25e28952d18ad32141c010bc258d50e383d4e
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724430"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>[セキュリティとコンプライアンス センター Office 365アカウントをユーザーにリダイレクトMicrosoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender
- Defender for Office 365

この記事では、以前の Office 365 セキュリティ とコンプライアンス センター (protection.office.com) から Microsoft 365 Defender (security.microsoft.com) への自動リダイレクトを有効にすることで、アカウントを Microsoft 365 Defender にルーティングする方法について説明します。

## <a name="what-to-expect"></a>想定される変化

自動リダイレクトが有効でアクティブになると、Office 365 Security and Compliance (protection.office.com) のセキュリティ関連機能にアクセスするユーザーは、自動的に Microsoft 365 Defender (security.microsoft.com) にルーティングされます。

変更された変更の詳細については[、「Microsoft Defender for Office 365」をMicrosoft 365 Defender。](microsoft-365-security-center-mdo.md)

自動リダイレクトが有効になっていると、ユーザーは Microsoft 365 Defender セキュリティ とコンプライアンス センターでセキュリティ機能を使用するときにOffice 365にルーティングされます。

これには、[脅威の管理] セクションの [アラート] ([アラートとアラート ポリシーの表示])、および [脅威管理] ダッシュボードとレポートの機能が含まれます。 セキュリティに関連Office 365セキュリティとコンプライアンス センター内のアイテムは、セキュリティにMicrosoft 365 Defender。

コンプライアンス関連のアイテムは Microsoft 365 コンプライアンス センター、メール フロー関連のアイテムは管理センター Exchangeにあります。

コンプライアンス関連または両方に対応する機能など、他のすべての機能は、リダイレクトの影響を受け取る必要があります。

### <a name="set-up-portal-redirection"></a>ポータルリダイレクトの設定

2021 年 10 月の初め現在、ポータルリダイレクトは自動的に、または既定で行われます。 ただし、一時的に無効にする必要がある場合は、これらの手順に従います。

<!--To start routing accounts to Microsoft 365 Defender at security.microsoft.com:

1. Make sure you're a global administrator or have security administrator permissions in Azure Active directory.
2. [Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.
3. Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.  
4. Toggle the Automatic redirection setting to **On**.
5. Click **Enable** to apply automatic redirection to Microsoft 365 Defender.

> [!NOTE]
> After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.-->

## <a name="can-i-go-back-to-using-the-former-portal"></a>以前のポータルを使用して戻ってみませんか?

何かが機能していない場合、または Microsoft 365 Defender を通じて完了できない場合は、ポータル フィードバック オプションを使用してその情報を確認します。 リダイレクトに関する問題が発生した場合は、お知らせください。

以前のポータルに戻すには、次の操作を行います。

1. [グローバル管理者](https://security.microsoft.com/)としてMicrosoft 365 Defenderサインインするか、Azure Active directory でセキュリティ管理者のアクセス許可を持つアカウントを使用します。

2. [電子 **メール**  >  **設定] &に**  >  **移動します**。

3. [自動リダイレクト] 設定を [オフ] に **切り替えます**。

4. メッセージが **表示されたら** 、[&フィードバックを共有する] をクリックします。

この設定は、いつでも再度有効にできます。

## <a name="related-information"></a>関連情報
- [Microsoft 365 Defender概要](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft は、セキュリティ操作を最新化するために統合された SIEM と XDR を提供します。](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR と SIEM のインフォグラフィック](https://afrait.com/blog/xdr-versus-siem/) 
- [`The New Defender`](https://afrait.com/blog/the-new-defender/) 
- [概要 Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft セキュリティ ポータルと管理センター](portals.md)
