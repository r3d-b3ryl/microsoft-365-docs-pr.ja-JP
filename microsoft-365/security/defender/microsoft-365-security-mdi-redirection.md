---
title: Microsoft Defender for IdentityからMicrosoft 365 Defenderへのアカウントのリダイレクト
description: アカウントとセッションを Defender for Identity から Microsoft 365 Defenderにリダイレクトする方法。
keywords: Microsoft 365 Defender、Microsoft 365 Defenderの概要、セキュリティ センターのリダイレクト
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
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b5c122f01d37d066e0f20bf817ca45ad5c57480b
ms.sourcegitcommit: 5fe7f2954a89406245416fc1a218cf4bf19abb85
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65864636"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-identity-to-microsoft-365-defender"></a>Microsoft Defender for IdentityからMicrosoft 365 Defenderへのアカウントのリダイレクト

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

このガイドでは、以前のMicrosoft Defender for Identity ポータル (portal.atp.azure.com) からMicrosoft 365 Defenderへの自動リダイレクトを有効にして、アカウントを<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>にルーティングする方法について説明します。

## <a name="what-to-expect"></a>想定される変化

自動リダイレクトが有効になると、portal.atp.azure.com の以前のMicrosoft Defender for Identity ポータルにアクセスするアカウントは、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">security.microsoft.com</a> のMicrosoft 365 Defender ポータルに自動的にルーティングされます。

## <a name="when-does-this-take-effect"></a>これはいつ有効になりますか?

有効にすると、この更新プログラムは、一部のアカウントでほぼすぐに有効になる可能性があります。 ただし、リダイレクトが組織内のすべてのアカウントに伝達されるまでに時間がかかる場合があります。 この設定が適用されている間、アクティブセッションのアカウントはセッションから取り出されず、現在のセッションを終了してもう一度サインインした後にのみMicrosoft 365 Defenderにルーティングされます。  

### <a name="set-up-portal-redirection"></a>ポータル リダイレクトを設定する

Microsoft 365 Defenderへのアカウントのルーティングを開始するには:

1. グローバル管理者であるか、Azure Active Directoryのセキュリティ管理者のアクセス許可があることを確認します。

1. Microsoft 365 Defenderにサインイン<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">します</a>。

1. **設定** > **Identities** > **General** > **Portal リダイレクト** に移動するか [、ここをクリックします](https://security.microsoft.com/preferences2/portal_redirection)。

    :::image type="content" source="../../media/portal-redirection.png" alt-text="ポータルリダイレクト。"lightbox="../../media/portal-redirection.png":::

1. [自動リダイレクト] 設定を **[オン]** に切り替えます。

>[!IMPORTANT]
>この設定を有効にした場合、アクティブなユーザー セッションは終了しません。 この設定が適用されている間にアクティブなセッションに参加しているアカウントは、現在のセッションを終了してもう一度サインインした後にのみMicrosoft 365 Defenderに送信されます。

>[!NOTE]
>この設定を有効または無効にするには、グローバル管理者であるか、Azure Active Directoryのセキュリティ管理者のアクセス許可が必要です。  

## <a name="can-i-go-back-to-using-the-former-portal"></a>以前のポータルの使用に戻ることはできますか?

何かがうまくいっていない場合、またはMicrosoft 365 Defenderを通じて完了できない場合は、そのことについてお聞かせたい場合があります。 リダイレクトに関する問題が発生した場合は、フィードバックの送信フォームを使用してお知らせください。

以前のMicrosoft Defender for Identity ポータルに戻すには:

1. グローバル管理者として<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>にサインインするか、Azure Active directory でセキュリティ管理者のアクセス許可を使用してアカウントを使用します。

2. **設定** > **Identities** > **General** > **Portal リダイレクト** に移動するか [、ここでページを開きます](https://security.microsoft.com/preferences2/portal_redirection)。  

3. [自動リダイレクト] 設定を **[オフ]** に切り替えます。

この設定は、いつでも再度有効にすることができます。

無効にすると、アカウントは security.microsoft.com にルーティングされなくなります。

## <a name="related-information"></a>関連情報

- [Microsoft 365 Defenderの概要](microsoft-365-defender.md)
- [Microsoft 365 Defenderについて](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender)
- [Microsoft セキュリティ ポータルと管理センター](portals.md)
