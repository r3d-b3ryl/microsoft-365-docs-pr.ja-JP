---
title: セキュリティ/コンプライアンス センターからOffice 365 Defender へのアカウントのリダイレクトMicrosoft 365する
description: Defender for Office 365 Defender Microsoft 365する方法。
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
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842522"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>セキュリティ/コンプライアンス センターから Office 365 Defender へのアカウントMicrosoft 365する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender
- Defender for Office 365

この記事では、以前の Office 365 セキュリティ/コンプライアンス センター (protection.office.com) から Microsoft 365 Defender (security.microsoft.com) への自動リダイレクトを有効にすることで、アカウントを Microsoft 365 Defender にルーティングする方法について説明します。

## <a name="what-to-expect"></a>想定される変化
自動リダイレクトが有効でアクティブになると、Office 365 Security and Compliance (protection.office.com) のセキュリティ関連機能にアクセスするユーザーは、Microsoft 365 Defender ( ) に自動的にルーティングされます https://security.microsoft.com) 。  

変更された変更の詳細については[、「Microsoft Defender for Office 365」をMicrosoft 365してください](microsoft-365-security-center-mdo.md)。

自動リダイレクトを有効にすると、ユーザーは Microsoft 365 セキュリティとコンプライアンス センターでセキュリティ機能を使用するときに、Office 365 Defender にルーティングされます。

これには、[脅威の管理] セクションと [脅威の管理] ダッシュボードとレポートの機能が含まれます。 セキュリティに関連Office 365セキュリティとコンプライアンス センター内のアイテムは、Defender にMicrosoft 365されません。

コンプライアンス関連のアイテムは、コンプライアンス センター Microsoft 365、メール フロー関連のアイテムは、Exchangeにあります。

コンプライアンス関連または両方に対応する機能など、他のすべての機能は、リダイレクトの影響を受け取る必要があります。 Office 365 Defender と Microsoft 365 コンプライアンス センターの両方Office 365、リダイレクトなしで表示されます。  

### <a name="set-up-portal-redirection"></a>ポータルリダイレクトの設定
アカウントのルーティングを開始するには、Microsoft 365で Defender に security.microsoft.com。

1. Azure Active directory で、グローバル管理者またはセキュリティ管理者のアクセス許可を持っている必要があります。
2. [Defender に](https://security.microsoft.com/)サインインMicrosoft 365します。
3. [電子 **メール**  >  **設定] &に**  >  **移動します**。  
4. [自動リダイレクト] 設定を [オン] に **切り替える**。
5. [有効 **にする] を** クリックして、Defender に自動リダイレクトMicrosoft 365適用します。

> [!NOTE]
> リダイレクトを有効にすると、この設定が適用されている間、アクティブなセッションのアカウントはセッションから取り出され、現在のセッションを終了して再度サインインした後にのみ Microsoft 365 Defender にルーティングされます。

## <a name="can-i-go-back-to-using-the-former-portal"></a>以前のポータルを使用して戻ってみませんか?
何かが機能していない場合、または Microsoft 365 Defender を通じて完了できないものがある場合は、ポータルフィードバックオプションを使用してそのことを聞きたいと思います。 リダイレクトに関する問題が発生した場合は、お知らせください。

以前のポータルに戻すには、次の操作を行います。

1. [グローバル管理者](https://security.microsoft.com/)としてMicrosoft 365 Defender にサインインするか、Azure Active directory でセキュリティ管理者のアクセス許可を持つアカウントを使用します。

2. [電子 **メール**  >  **設定] &に**  >  **移動します**。   

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
