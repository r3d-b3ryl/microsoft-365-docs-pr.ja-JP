---
title: (偽陽性) Microsoft Defender for Office 365 を使用して、配信がブロックされる正当なメールを処理する方法
description: ビジネスの失われるのを防ぐためにMicrosoft Defender for Office 365によってブロックされる正当な電子メール (False Positive) を処理する手順。
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: jarogers
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: abf348fd4de02f521dfa9c5f8d7c16346753c5de
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66994321"
---
# <a name="how-to-handle-legitimate-emails-getting-blocked-false-positive-using-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365を使用して、ブロックされる正当な電子メール (False Positive) を処理する方法

Microsoft Defender for Office 365は、脅威として誤ってブロックされている重要な正当なビジネス 電子メール (False Positives) に対処するのに役立ちます。 Defender for Office 365は、管理者が正当なメールがブロックされている *理由*、状況を迅速に解決する方法、および今後同様の状況が発生するのを防ぐ方法を理解するのに役立ちます。

## <a name="what-youll-need"></a>必要なもの

- Microsoft Defender for Office 365プラン 1 または 2 (E5 の一部として含まれます)。 Exchange Online顧客はこの機能を利用することもできます。
- 十分なアクセス許可 (セキュリティ管理者ロール)。
- 次の手順を実行するには、5 分から 10 分かかります。

## <a name="handling-legitimate-emails-in-to-junk-folder-of-end-users"></a>エンド ユーザーの迷惑メール フォルダーへの正当なメールの処理

1. Microsoft Message アドインまたは Outlook ボタンを使用して、エンド ユーザーに迷惑メール **として** 報告するように依頼します。
2. エンド ユーザーは、Outlook の [**差出人セーフ リストに送信者**](https://support.microsoft.com/en-us/office/safe-senders-in-outlook-com-470d4ee6-e3b6-402b-8cd9-a6f00eda7339) を追加して、これらの送信者からの電子メールが迷惑メール フォルダーに表示されないようにすることもできます。
3. 管理者は、ユーザーから報告されたコンテンツ ポータルから [ユーザーから報告されたメッセージを](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#view-user-submissions-to-microsoft&preserve-view=true) トリアージできます。
4. これらの報告されたメッセージから、管理者は [**分析のために Microsoft**](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#notify-users-from-within-the-portal&preserve-view=true) に送信でき、その電子メールが最初にブロックされた理由を理解できます。
5. 必要に応じて、分析のために Microsoft に送信するときに、管理者は送信者が問題を軽減するための [**許可**](/microsoft-365/security/office-365-security/manage-tenant-allows?view=o365-worldwide#add-sender-allows-using-the-submissions-portal&preserve-view=true)を慎重に作成できます。
6. 管理者申請の結果が表示されたら、メールがブロックされた理由と、テナントのセットアップを改善して、同様の状況が今後発生 *するのを防ぐ* 方法を理解してください。

## <a name="handling-legitimate-emails-that-are-in-quarantine-folder-of-end-users"></a>エンド ユーザーの検疫フォルダーにある正当な電子メールの処理

1. エンド ユーザーは、セキュリティ管理者が有効にした設定に従って、検疫されたメッセージに関する [電子メール ダイジェスト](/microsoft-365/security/office-365-security/use-spam-notifications-to-release-and-report-quarantined-messages?view=o365-worldwide&preserve-view=true) を受信します。
2. エンド ユーザーは、検疫内のメッセージをプレビューしたり、送信者をブロックしたり、メッセージを解放したり、それらのメッセージを分析のために Microsoft に送信したり、管理者からそれらのメールのリリースを要求したりできます。

## <a name="handling-legitimate-emails-in-quarantine-folder-of-an-admin"></a>管理者の検疫フォルダー内の正当なメールを処理する

1. 管理者は、検疫されたメール (リリースを要求するアクセス許可を求めるメールを含む) を [レビュー ページ](/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files?view=o365-worldwide&preserve-view=true)から表示できます。
2. 管理者は、分析のために Microsoft にメッセージを送信している間に検疫からメッセージを解放し、状況を軽減するための許可を作成できます。
3. 提出の結果が得られたら、管理者は判定を読んで、メールがブロックされた理由と、テナントの設定を改善して、同様の状況が今後起こるのを防ぐ方法を理解する必要があります。
