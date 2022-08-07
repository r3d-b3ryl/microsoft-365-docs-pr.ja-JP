---
title: キャンペーン用の Microsoft 365 のセットアップの概要
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 08/05/2022
ms.collection:
- M365-Campaigns
- m365solution-smb
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: キャンペーンや他の企業用の Microsoft 365 Business のセットアップの概要
ms.openlocfilehash: 90de3294ffb7bfe1ebc2890375433ba432cdca4c
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276834"
---
# <a name="setup-for-microsoft-365-business-for-campaigns"></a>キャンペーン用の Microsoft 365 Business をセットアップする

[Microsoft 365 for Campaigns にサブスクライブした](get-microsoft-365-campaigns.md)後、次の手順はすべてを設定することです。

## <a name="before-you-begin"></a>開始する前に

セットアップ プロセスを開始する前に、次の要件を満たしていることを確認してください。

| 要件 | 説明 |
|:---|:---|
| サブスクリプション | Microsoft 365 Business Premium または Microsoft 365 for Campaigns <br/><br/> 試用版を開始する、またはサブスクリプションを購入するには、次の記事を参照してください。 <br/>- [Microsoft 365 Business Premium を入手する](get-microsoft-365-business-premium.md)<br/>- [Microsoft 365 for Campaigns を入手する](get-microsoft-365-campaigns.md) |
| アクセス許可  | 初期セットアップの手順を完了するには、グローバル管理者である必要があります。[管理者ロールの詳細を参照してください](../admin/add-users/about-admin-roles.md)。 |
| ブラウザー要件 | Microsoft Edge、Safari、Chrome または Firefox。 [ブラウザー要件の詳細を参照してください](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources#coreui-heading-uyetipy)。  |
| オペレーティング システム (クライアント) | **Windows**:  Windows 11、Windows 10、Windows 8.1<br/>**MacOS**: 最新の 3 つのバージョンのいずれか。 
| オペレーティング システム (サーバー) | Windows Server または Linux Server <br/>- Microsoft Defender for Business サーバーが必要です (現在プレビュー段階)<br/>- 「[Microsoft Defender for Business サーバーの取得方法 (プレビュー)](../security/defender-business/get-defender-business-servers.md)」を参照してください。  |

> [!TIP]
> Microsoft 365、Office、システム要件の詳細については、「[Microsoft 365 および Office のリソース](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)」を参照してください。

## <a name="sign-in-to-microsoft-365-for-campaigns"></a>Microsoft 365 for Campaigns にサインインする

Microsoft 365 for Campaigns (または Microsoft 365 Business Premium) にサインアップした場合は、Microsoft 365 管理者 (グローバル管理者とも呼ばれます) として指定されます。 これにより、サインインしてシステムを開始できます。

サインインする方法は次のとおりです。

1. [Microsoft 365 for Campaigns にサインアップ](m365-campaigns-sign-up.md) したときに使用したメール アドレスに送信されたユーザー名とパスワードを見つけます。

2. ブラウザーで、<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank"><https://admin.microsoft.com></a> の Microsoft 365 管理センターに移動します。

3. ユーザー名とパスワードを入力します。 [**サインイン**] を選びます。

4. ページの右上で、コントロールの [**プレビュー**] を見つけます。 [[キャンペーンのバンプアップ保護](m365bp-security-overview.md)] で説明されているすべてのコントロールを使用できるように、[**プレビュー**] を選択します。

## <a name="how-your-staff-will-sign-in"></a>スタッフがサインインする方法

Microsoft 365 for Campaigns (または Microsoft 365 Business Premium) サブスクリプションに追加されたユーザーは、次の手順に従ってサインインできます。

1. <a href="https://office.com" target="_blank"><https://Office.com></a> に移動します。

2. アカウントのユーザー名とパスワードを使用してサインインします。 ユーザーは、ユーザーとして追加されたときに受信するメールにこの情報が含まれます。 メールが見つからない場合は、「[ユーザーが招待メールを受信しなかった場合](../admin/simplified-signup/admin-invite-business-standard.md#i-shared-an-email-invite-but-the-user-didnt-receive-the-email)」 を参照してください。

> [!TIP]
> サインイン、Office アプリの取得、ファイルの保存、コピー、共有に関するヘルプについては、[従業員クイック セットアップ ガイド](../admin/setup/employee-quick-setup.md) へのリンクをスタッフに提供します。

## <a name="customize-your-sign-in-page-with-a-privacy-and-consent-notice"></a>プライバシーと同意の通知を使用してサインイン ページをカスタマイズする

ビジネスやキャンペーンは、サインイン ページにプライバシーと同意の通知を追加することにより、法執行機関がオンラインの犯罪者に対して法的請求を行うことを容易にすることができます。

サインイン ページは、ブランドに合わせてカスタマイズできます。 また、ユーザーがサインインするのに役立つテキストを追加したり、Microsoft 365 リソースにアクセスするための法的要件や制限を指摘したりすることもできます。

## <a name="customize-the-text-on-your-sign-in-page"></a>サインイン ページのテキストをカスタマイズする

サインイン ページのカスタマイズ可能な要素を更新するには、グローバル管理者である必要があります。 具体的な手順については、[会社のブランディングの追加](/azure/active-directory/fundamentals/customize-branding)に関する記事を参照してください。

更新できる要素は次のとおりです。

- サインイン ページ テキスト (プライバシーと同意に関する声明を簡単に追加できる場所)
- サインイン ページの背景画像
- バナー ロゴ
- ユーザー名ヒント フィールド

プライバシーと同意に関する通知の例については、「[コンピューターの検索と押収、および犯罪捜査における電子証拠の取得](https://www.justice.gov/sites/default/files/criminal-ccips/legacy/2015/01/14/ssmanual2009.pdf)」の付録 A を参照してください。

## <a name="visual-guide-help-protect-yourself-and-your-campaign-from-digital-threats"></a>ビジュアル ガイド: デジタルの脅威から自分とキャンペーンを保護するのに役立ちます

スタッフがサイバー脅威からキャンペーンを保護する手順について学習できるように、次のダウンロード 可能なガイドを使用します。

[![キャンペーン情報グラフィックを保護するためのセキュリティで保護された画像。](../media/M365-Campaigns-WhatCanUsersDoToSecure-358x201.png)](https://download.microsoft.com/download/f/c/5/fc58bc0c-773a-4ac8-a232-6f986f61ef58/M365CampaignsWhatCanUsersDoToSecure.pdf)

[PDF](https://download.microsoft.com/download/f/c/5/fc58bc0c-773a-4ac8-a232-6f986f61ef58/M365CampaignsWhatCanUsersDoToSecure.pdf) | [PowerPoint](https://download.microsoft.com/download/f/c/5/fc58bc0c-773a-4ac8-a232-6f986f61ef58/M365CampaignsWhatCanUsersDoToSecure.pptx)

## <a name="next-objective"></a>次の目標

[セキュリティの強化](m365bp-security-overview.md)に進みます。
