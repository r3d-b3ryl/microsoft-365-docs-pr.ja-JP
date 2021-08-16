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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 518cf05d271c534caa2e0d1c6aafe854aa1da0b7ee4874bc42d57fa20c27bb48
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53873441"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>[セキュリティとコンプライアンス センター Office 365アカウントをユーザーにリダイレクトMicrosoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender
- Defender for Office 365

この記事では、以前の Office 365 セキュリティ とコンプライアンス センター (protection.office.com) から Microsoft 365 Defender (security.microsoft.com) への自動リダイレクトを有効にすることで、アカウントを Microsoft 365 Defender にルーティングする方法について説明します。

## <a name="what-to-expect"></a>想定される変化
自動リダイレクトが有効でアクティブになると、Office 365 Security and Compliance (protection.office.com) のセキュリティ関連機能にアクセスするユーザーは、自動的に Microsoft 365 Defender ( ) にルーティングされます https://security.microsoft.com) 。  

変更された変更の詳細については[、「Microsoft Defender for Office 365」をMicrosoft 365 Defender。](microsoft-365-security-center-mdo.md)

自動リダイレクトが有効になっていると、ユーザーは Microsoft 365 Defender セキュリティ とコンプライアンス センターでセキュリティ機能を使用するときにOffice 365にルーティングされます。

これには、[脅威の管理] セクションと [脅威の管理] ダッシュボードとレポートの機能が含まれます。 セキュリティに関連Office 365セキュリティとコンプライアンス センター内のアイテムは、セキュリティにMicrosoft 365 Defender。

コンプライアンス関連のアイテムは Microsoft 365 コンプライアンス センター、メール フロー関連のアイテムは管理センター Exchangeにあります。

コンプライアンス関連または両方に対応する機能など、他のすべての機能は、リダイレクトの影響を受け取る必要があります。 Office 365通知は、リダイレクトMicrosoft 365 Defender、Office 365とコンプライアンス センターの両方に表示されます。  

### <a name="set-up-portal-redirection"></a>ポータルリダイレクトの設定
アカウントのルーティングを開始するには、Microsoft 365 Defenderで security.microsoft.com。

1. Azure Active directory で、グローバル管理者またはセキュリティ管理者のアクセス許可を持っている必要があります。
2. [サインインして](https://security.microsoft.com/)、Microsoft 365 Defender。
3. [電子 **メール**  >  **設定] &に**  >  **移動します**。  
4. [自動リダイレクト] 設定を [オン] に **切り替える**。
5. [有効 **にする]** をクリックして、自動リダイレクトをMicrosoft 365 Defender。

> [!NOTE]
> リダイレクトを有効にすると、この設定が適用されている間、アクティブなセッションのアカウントはセッションから取り出され、現在のセッションを終了して再びサインインした後にのみ Microsoft 365 Defender にルーティングされます。

## <a name="can-i-go-back-to-using-the-former-portal"></a>以前のポータルを使用して戻ってみませんか?
何かが機能していない場合、または Microsoft 365 Defender を通じて完了できない場合は、ポータル フィードバック オプションを使用してその情報を確認します。 リダイレクトに関する問題が発生した場合は、お知らせください。

以前のポータルに戻すには、次の操作を行います。

1. [グローバル管理者](https://security.microsoft.com/)としてMicrosoft 365 Defenderサインインするか、Azure Active directory でセキュリティ管理者のアクセス許可を持つアカウントを使用します。

2. [電子 **メール**  >  **設定] &に**  >  **移動します**。

3. [自動リダイレクト] 設定を [オフ] に **切り替えます**。

4. メッセージが **表示されたら** 、[&フィードバックを共有する] をクリックします。

この設定は、いつでも再度有効にできます。

## <a name="related-information"></a>関連情報
- [Microsoft 365 Defender概要](overview-security-center.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft は、セキュリティ操作を最新化するために統合された SIEM と XDR を提供します。](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR と SIEM のインフォグラフィック](https://afrait.com/blog/xdr-versus-siem/) 
- [新しい Defender](https://afrait.com/blog/the-new-defender/) 
- [概要 Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft セキュリティ ポータルと管理センター](portals.md)
