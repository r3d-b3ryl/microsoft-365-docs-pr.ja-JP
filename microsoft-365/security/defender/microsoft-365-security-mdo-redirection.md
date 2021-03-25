---
title: Microsoft Defender for Office 365 から新しい Microsoft 365 セキュリティ センターへのアカウントのリダイレクト
description: Defender for Office 365 セキュリティ センターにリダイレクトする方法。
keywords: Microsoft 365 セキュリティ センター、Microsoft 365 セキュリティ センターの使用開始、セキュリティ センターのリダイレクト
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064643"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Microsoft Defender for Office 365 から Microsoft 365 セキュリティ センターへのリダイレクト

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender
- Defender for Office 365

この記事では、以前の Microsoft セキュリティ/コンプライアンス センター (protection.office.com または securitycenter.microsoft.com) から Microsoft 365 セキュリティ センター (security.microsoft.com) への自動リダイレクトを有効にすることで、アカウントを Microsoft 365 セキュリティ センターにルーティングする方法について説明します。

>[!NOTE]
> ポータル リダイレクト機能は、365 E5 および Microsoft Defender Office P2 のお客様Office使用できます。

## <a name="what-to-expect"></a>想定される変化
自動リダイレクトが有効でアクティブになると、Office 365 セキュリティとコンプライアンス (protection.office.com) のセキュリティ関連機能にアクセスするユーザーは、Microsoft 365 セキュリティ センター () に自動的にルーティングされます。 https://security.microsoft.com)  

変更点について詳しくは [、Microsoft 365](microsoft-365-security-center-mdo.md)セキュリティ センターの microsoft Defender for Office 365 をご覧ください。

自動リダイレクトを有効にすると、ユーザーは Office 365 セキュリティ とコンプライアンス センターでセキュリティ機能を使用するときに Microsoft 365 セキュリティ センターにルーティングされます。

これには、[脅威の管理] セクションと [脅威の管理] ダッシュボードとレポートの機能が含まれます。 セキュリティに関連Office 365 セキュリティ およびコンプライアンス センター内のアイテムは、Microsoft 365 セキュリティ センターにリダイレクトされません。

コンプライアンス関連のアイテムは Microsoft 365 コンプライアンス センターで見つかり、メール フロー関連のアイテムは Exchange 管理センターにあります。

コンプライアンス関連または両方に対応する機能など、他のすべての機能は、リダイレクトの影響を受け取る必要があります。 Office 365 セキュリティ 通知は、リダイレクトなしで、Microsoft 365 セキュリティ センターと Office 365 セキュリティ/コンプライアンス センターの両方に表示されます。  

### <a name="set-up-portal-redirection"></a>ポータルリダイレクトの設定
Microsoft 365 セキュリティ センターへのアカウントのルーティングを開始するには、次 security.microsoft.com。

1. Azure Active directory で、グローバル管理者またはセキュリティ管理者のアクセス許可を持っている必要があります。
2. [](https://security.microsoft.com/) Microsoft 365 セキュリティ センターにサインインします。
3. [設定] **[**  >  **電子メール] &ポータル**  >  **リダイレクト] に移動します**。  
4. [自動リダイレクト] 設定を [オン] に **切り替える**。
5. [ **有効にする]** をクリックして、Microsoft 365 セキュリティ センター ポータルに自動リダイレクトを適用します。

> [!NOTE]
> リダイレクトを有効にすると、この設定が適用されている間、アクティブなセッションのアカウントはセッションから取り出され、現在のセッションを終了して再びサインインした後にのみ、Microsoft 365 セキュリティ センターにルーティングされます。

## <a name="can-i-go-back-to-using-the-former-portal"></a>以前のポータルを使用して戻ってみませんか?
何かが機能していない場合、または Microsoft 365 セキュリティ センター ポータルで完了できない場合は、ポータル フィードバック オプションを使用して説明します。 リダイレクトに関する問題が発生した場合は、プライベート プレビューを通じて PM バディに直接連絡するか、[フィードバックの送信] フォームから連絡してください。

以前のポータルに戻すには、次の操作を行います。

1. [](https://security.microsoft.com/) Microsoft 365 セキュリティ センターにグローバル管理者としてサインインするか、Azure Active directory でセキュリティ管理者のアクセス許可を使用してアカウントを使用します。

2. [設定エンドポイント **]**  >  **[全般ポータル**  >  **]**  >  **リダイレクトに移動します**。  

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
- [Microsoft 365 Defender について](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft セキュリティ ポータルと管理センター](portals.md)