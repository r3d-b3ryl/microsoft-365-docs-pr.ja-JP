---
title: Microsoft Defender から新しいセキュリティ センター Office 365アカウントをMicrosoft 365する
description: Defender for Office 365セキュリティ センター Microsoft 365する方法。
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
ms.openlocfilehash: 40d86f9f3a4896bbe788f0a9894a7e08efe3a690
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301730"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Microsoft Defender からセキュリティ センター Office 365アカウントMicrosoft 365リダイレクトする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender
- Defender for Office 365

この記事では、以前の Microsoft Security and Compliance Center (protection.office.com または securitycenter.microsoft.com) から Microsoft 365 セキュリティ センター (security.microsoft.com) への自動リダイレクトを有効にすることで、アカウントを Microsoft 365 セキュリティ センターにルーティングする方法について説明します。

## <a name="what-to-expect"></a>想定される変化
自動リダイレクトが有効でアクティブになると、Office 365 セキュリティとコンプライアンス (protection.office.com) のセキュリティ関連機能にアクセスするユーザーは、Microsoft 365 セキュリティ センター ( ) に自動的にルーティングされます。 https://security.microsoft.com)  

変更された変更の詳細については[、「Microsoft Defender for Office 365セキュリティ センター Microsoft 365参照してください](microsoft-365-security-center-mdo.md)。

自動リダイレクトを有効にすると、ユーザーは Microsoft 365 セキュリティ とコンプライアンス センターでセキュリティ機能を使用するときに、Office 365 セキュリティ センターにルーティングされます。

これには、[脅威の管理] セクションと [脅威の管理] ダッシュボードとレポートの機能が含まれます。 セキュリティに関連Office 365セキュリティとコンプライアンス センター内のアイテムは、セキュリティ センター Microsoft 365されません。

コンプライアンス関連のアイテムは、コンプライアンス センター Microsoft 365、メール フロー関連のアイテムは、Exchangeにあります。

コンプライアンス関連または両方に対応する機能など、他のすべての機能は、リダイレクトの影響を受け取る必要があります。 Office 365は、リダイレクトなしで、Microsoft 365 セキュリティ センターと Office 365 コンプライアンス センターの両方に表示されます。  

### <a name="set-up-portal-redirection"></a>ポータルリダイレクトの設定
アカウントのルーティングを開始するには、Microsoft 365でセキュリティ センター security.microsoft.com。

1. Azure Active directory で、グローバル管理者またはセキュリティ管理者のアクセス許可を持っている必要があります。
2. [セキュリティ センター](https://security.microsoft.com/)にサインインMicrosoft 365します。
3. [電子 **メール**  >  **設定] &に**  >  **移動します**。  
4. [自動リダイレクト] 設定を [オン] に **切り替える**。
5. [**有効にする]** をクリックして、セキュリティ センター ポータルMicrosoft 365リダイレクトを適用します。

> [!NOTE]
> リダイレクトを有効にすると、この設定が適用されている間、アクティブなセッションのアカウントはセッションから取り出されません。現在のセッションを終了して再度サインインした後にのみ、Microsoft 365 セキュリティ センターにルーティングされます。

## <a name="can-i-go-back-to-using-the-former-portal"></a>以前のポータルを使用して戻ってみませんか?
何かが機能していない場合、または Microsoft 365 セキュリティ センター ポータルで完了できない場合は、ポータル フィードバック オプションを使用してその情報を確認します。 リダイレクトに関する問題が発生した場合は、プライベート プレビューを通じて PM バディに直接連絡するか、[フィードバックの送信] フォームから連絡してください。

以前のポータルに戻すには、次の操作を行います。

1. [Azure](https://security.microsoft.com/) Active directory で、Microsoft 365管理者として、またはセキュリティ管理者のアクセス許可を持つアカウントを使用して、セキュリティ センターにサインインします。

2. [エンドポイントの全般 **設定**  >  **リダイレクト**  >  **]**  >  **に移動します**。  

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
