---
title: 利用状況分析Microsoft 365トラブルシューティング
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Microsoft 365 Usage Analytics テンプレート アプリに関する問題のトラブルシューティング方法について説明します。
ms.openlocfilehash: afa9841b38beefcfdd091f27e7b1f328cdf52a5e
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531077"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>利用状況分析Microsoft 365トラブルシューティング

次のエラー メッセージの一覧を調べて、Microsoft 365利用状況分析に関する最も一般的な問題について説明します。
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>リクエストを処理できません。 最初にMicrosoft 365 管理センターからこのデータをサブスクライブする必要があります。

 **エラー コード:** 422 
  
 **このメッセージが表示される場所:** Microsoft 365 Usage Analytics テンプレート アプリに接続するとき、または Microsoft 365 Reporting API を直接呼び出すときにPower BI。 
  
 **原因：** アプリに接続する前に、Microsoft 365 管理センターからデータをサブスクライブする必要があります。 この手順を最初に行わないと、Microsoft 365テナント ID を指定した場合でも、テンプレート アプリに接続できません。 
  
 **このエラーを修正するには:** データをサブスクライブするには、管理センター\>の **[レポート** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">の使用状況</a>] に移動し、メイン ダッシュボード ページの [Microsoft 365利用状況分析] タイルを見つけます。 **[概要**] ボタンを選択し、開いた [**レポート**] ウィンドウで、[**Power BIの利用状況分析をMicrosoft 365データを使用できるようにする**] 設定と **[保存]** をオンにします。
  
## <a name="we-are-processing-your-data"></a>データを処理しています

 **このメッセージが表示される場所:** Microsoft 365 管理センターの **[利用状況**] ダッシュボードの [Microsoft 365 **利用状況** 分析] タイル。 
  
 **原因：** Microsoft 365 管理センターから [テンプレート アプリにデータを表示することを選択](enable-usage-analytics.md)すると、Microsoft 365 システムは組織の使用状況履歴データの生成を開始します。 テナントのサイズによっては、この手順に 2 時間から 48 時間かかることがあります。 
  
 **これを修正するには:** お待ちください。ただし、メッセージが 3 日後にデータに変更されない場合 **は**、[ビジネス サポートのMicrosoft 365にお問い合わせください](サポートを受ける](../get-help-support.md)。
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>現在、リクエストを処理できません。引き続き組織のデータを準備しています。

 **エラー コード:** 423 
  
 **このメッセージが表示される場所:** Power BIでは、Microsoft 365 Usage Analytics テンプレート アプリに接続するとき、または Microsoft 365 Reporting API を直接呼び出すとき。 
  
 **原因：** 管理センターから [テンプレート アプリにデータを表示することを選択](enable-usage-analytics.md)すると、Microsoft 365 システムは組織の使用状況履歴データの生成を開始します。 テナントのサイズによっては、この手順には 2 時間から 48 時間かかる場合があります。 
  
 **これを修正するには:** お待ちくださいが、メッセージが開始から 3 日間でも **データ** に変更されない場合は、[ビジネス サポートのMicrosoft 365にお問い合わせください](../../business-video/get-help-support.md)。
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>入力したテナント ID の形式が間違っています

 **エラー コード:** 400 
  
 **このメッセージが表示される場所:** Power BIでは、Microsoft 365 Usage Analytics テンプレート アプリに接続するとき、または Microsoft 365 Reporting API を直接呼び出すとき。 
  
 **原因：** テナント ID は guid であり、xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxx の形式である必要があります。 テナント入力ボックスに他の文字列を入力すると、このエラーが発生します。 
  
 **このエラーを修正するには:** 管理センター\>の **[レポート** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">の使用状況]</a> に移動し、メイン ダッシュボード ページの [Microsoft 365利用状況分析] タイルを見つけます。 テナント ID がタイルに一覧表示されます。 ここからコピーし、テンプレート アプリに接続するためのダイアログ ボックスに貼り付けることができます。 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>入力したテナント ID が弊社のシステムで認識されません

 **エラー コード:** 404 
  
 **このメッセージが表示される場所:** Microsoft 365 Usage Analytics テンプレート アプリに接続するとき、または Microsoft 365 Reporting API を直接呼び出すときにPower BI。 
  
 **原因：** 指定したテナント ID が無効であるか、存在しません。 
  
 **このエラーを修正するには:** 管理センター\>の **[レポート** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">の使用状況]</a> に移動し、メイン ダッシュボード ページの [Microsoft 365利用状況分析] タイルを見つけます。 テナント ID がタイルに一覧表示されます。 ここからコピーし、テンプレート アプリに接続するためのダイアログ ボックスに貼り付けることができます。 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>資格情報を再入力して Power BI にもう一度サインインしてください

エラー コード:302
  
 **このメッセージが表示される場所:** Microsoft 365 Usage Analytics テンプレート アプリに接続するとき、または Microsoft 365 Reporting API を直接呼び出すときにPower BI。 
  
 **原因:** 認証コードが不合格となり、資格情報の再入力が求められている可能性があります。 
  
 **修正方法:** Power BI からサインアウトし、もう一度サインインします。 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>このデータにアクセスする権限がありません。このサービスからデータにアクセスする権限を取得できるようにするには、グローバル管理者か、いずれかの製品管理者である必要があります。

 **エラー コード:** 403 
  
 **このメッセージが表示される場所:** Microsoft 365 Usage Analytics テンプレート アプリに接続するとき、または Microsoft 365 Reporting API を直接呼び出すときにPower BI。 
  
 **原因：** テンプレート アプリに接続しようとしたユーザーに、このデータにアクセスするための適切なレベルの承認がないため、承認コードが失敗しました。 
  
 **このエラーを修正するには:****グローバル管理者**、**Exchange管理者、Skype for Business管理者**、**SharePoint管理者**、**グローバル リーダー**、**またはレポート リーダー** のいずれかであるユーザーの資格情報を指定して、テンプレート アプリに接続します。 詳細については、「 [管理者ロールについて](../add-users/about-admin-roles.md) 」を参照してください。 
  
## <a name="refresh-failed"></a>更新が失敗しました

 **このメッセージが表示される場所:** Power BI からの電子メールまたは更新履歴の失敗した状態。 
  
 **原因：** テンプレート アプリに接続したユーザーの資格情報がリセットされ、テンプレート アプリの接続設定で更新されず、更新エラーが表示されることがあります。 
  
 **このエラーを修正するには:** Power BIで、Microsoft 365 Usage Analytics テンプレート アプリに対応するデータセットを見つけ、**スケジュール更新** を選択し、管理者資格情報を指定します。 
  
それでも問題が解決しない場合は、キャッシュをクリアし、テンプレート アプリを再作成します。
  
  
