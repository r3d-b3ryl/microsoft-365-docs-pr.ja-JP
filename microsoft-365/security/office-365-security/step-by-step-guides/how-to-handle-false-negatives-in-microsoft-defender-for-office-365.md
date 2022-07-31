---
title: (偽陰性) Microsoft Defender for Office 365 を使用して、受信者に配信された悪意のあるメールを処理する方法
description: ビジネスの損失を防ぐために、エンド ユーザーと受信トレイに送信される悪意のある電子メールを処理する手順 (False Negatives として) Microsoft Defender for Office 365。
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
ms.openlocfilehash: decbece049ea4f91deb529d2fd640816bf3f1d0c
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66994260"
---
# <a name="how-to-handle-malicious-emails-that-are-delivered-to-recipients-false-negatives-using-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365を使用して、受信者に配信された悪意のある電子メール (False Negatives) を処理する方法

Microsoft Defender for Office 365は、受信者に配信され、組織の生産性を危険にさらす悪意のあるメール (False Negative) に対処するのに役立ちます。
Defender for Office 365は、メールが配信される理由、状況を迅速に解決する方法、および同様の状況が今後発生するのを防ぐ方法を理解するのに役立ちます。

## <a name="what-youll-need"></a>必要なもの

- Microsoft Defender for Office 365プラン 1 と 2 (E5 の一部として含まれています)。 Exchange Online顧客はこれを利用することもできます。
- 十分なアクセス許可 (セキュリティ管理者ロール)。
- 次の手順を実行するには、5 分から 10 分かかります。

## <a name="handling-malicious-emails-in-the-inbox-folder-of-end-users"></a>エンド ユーザーの受信トレイ フォルダーで悪意のあるメールを処理する

1. Microsoft メッセージ アドインまたは Microsoft フィッシング アドインまたは Outlook ボタンを使用して、エンド ユーザーに **メールをフィッシング** または **迷惑** メールとして報告するように依頼します。
2. エンド ユーザーは、Outlook の [ブロック送信者リストに送信者](https://support.microsoft.com/en-us/office/block-a-mail-sender-b29fd867-cac9-40d8-aed1-659e06a706e4#:~:text=1%20On%20the%20Home%20tab%2C%20in%20the%20Delete,4%20Click%20OK%20in%20both%20open%20dialog%20boxes..) を追加して、この送信者からの電子メールが受信トレイに配信されないようにすることもできます。
3. 管理者は、ユーザーが報告したコンテンツ ポータルから [ユーザーが報告したメッセージを](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#view-user-submissions-to-microsoft&preserve-view=true) トリアージできます。
4. これらの報告されたメッセージから、管理者は [分析のために Microsoft](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#notify-users-from-within-the-portal&preserve-view=true) **に送信** して、最初にその電子メールが許可された理由を確認できます。
5. 必要に応じて、分析のために Microsoft に送信するときに、管理者は [送信者が問題を軽減するためのブロック](/microsoft-365/security/office-365-security/manage-tenant-blocks?view=o365-worldwide&preserve-view=true) を作成できます。
6. 提出の結果が得られたら、判定を読んで、メールが許可された理由と、テナントの設定を改善して、同様の状況が今後起こるのを防ぐ方法を理解してください。

## <a name="handling-malicious-emails-in-junk-folder-of-end-users"></a>エンド ユーザーの迷惑メール フォルダー内の悪意のあるメールの処理

1. Microsoft メッセージ アドイン、Microsoft フィッシング アドイン、または Outlook ボタンを使用して、エンド ユーザーに **フィッシング** として電子メールを報告するように依頼します。
2. 管理者は、ユーザーが報告したコンテンツ ポータルから [報告されたメッセージをトリ](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#view-user-submissions-to-microsoft&preserve-view=true) アージできます。
3. これらの報告されたメッセージから、管理者は [分析のために Microsoft](/microsoft-365/security/office-365-security/admin-submission?view=o365-worldwide#notify-users-from-within-the-portal&preserve-view=true) **に送信** し、その電子メールが最初に許可された理由を確認できます。
4. 必要に応じて、分析のために Microsoft に送信するときに、管理者は [送信者が問題を軽減するためのブロック](/microsoft-365/security/office-365-security/manage-tenant-blocks?view=o365-worldwide&preserve-view=true) を作成できます。
5. 提出の結果が得られたら、判定を読んで、メールが許可された理由と、テナントの設定を改善して、同様の状況が今後起こるのを防ぐ方法を理解してください。

## <a name="handling-malicious-emails-landing-in-the-quarantine-folder-of-end-users"></a>エンド ユーザーの検疫フォルダーにランディングする悪意のある電子メールの処理

1. エンド ユーザーは、管理者が有効にした設定に従って、検疫されたメッセージに関する [電子メール ダイジェスト](/microsoft-365/security/office-365-security/use-spam-notifications-to-release-and-report-quarantined-messages?view=o365-worldwide&preserve-view=true) を受け取ります。
2. エンド ユーザーは、検疫内のメッセージをプレビューし、送信者をブロックし、分析のためにそれらのメッセージを Microsoft に送信できます。

## <a name="handling-malicious-emails-landing-in-the-quarantine-folder-of-admins"></a>管理者の検疫フォルダーにランディングする悪意のある電子メールの処理

1. 管理者は、検疫されたメール (リリースを要求するアクセス許可を求めるメールを含む) を [レビュー ページ](/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files?view=o365-worldwide&preserve-view=true)から表示できます。
2. 管理者は、分析のために悪意のあるメッセージや疑わしいメッセージを Microsoft に送信し、判定を待っている間に状況を軽減するためのブロックを作成できます。
3. 提出の結果が表示されたら、判定を読んで、メールが許可された理由と、テナントのセットアップを改善して、同様の状況が今後発生するのを防ぐ方法について説明します。
