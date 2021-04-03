---
title: Microsoft 365 利用状況分析のトラブルシューティング
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Microsoft 365 Usage Analytics テンプレート アプリの問題をトラブルシューティングする方法について説明します。
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580740"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析のトラブルシューティング

Microsoft 365 使用状況分析に関する最も一般的な問題に関するヘルプを表示するには、次のエラー メッセージの一覧を参照してください。
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>リクエストを処理できません。 まず、Microsoft 365 管理センターからこのデータをサブスクライブする必要があります。

 **エラー コード:** 422 
  
 **このメッセージが表示される場所:** Power BI で Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 Reporting API を直接呼び出す場合。 
  
 **原因:** アプリに接続する前に、Microsoft 365 管理センターのデータをサブスクライブする必要があります。 この手順を最初に実行しない場合は、Microsoft 365 テナント ID を指定した場合でも、テンプレート アプリに接続できません。 
  
 **このエラーを修正するには、次の手順を実行します。** データをサブスクライブするには、管理センターの [利用状況のレポート] に移動し、メイン ダッシュボード ページで \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>[Microsoft 365 利用状況分析] タイルを探します。 [開始 **する] ボタンを** 選択し、開く [レポート] ウィンドウで、[Power BI の **Microsoft 365** 利用状況分析でデータを使用できる] 設定をオンにし、[保存] を **オンにします**。
  
## <a name="we-are-processing-your-data"></a>データを処理しています

 **このメッセージが表示される場所:** Microsoft **365 管理** センターの利用状況ダッシュボードの[Microsoft 365 使用状況分析] タイルで指定します。 
  
 **原因:** Microsoft [](enable-usage-analytics.md) 365 管理センターからテンプレート アプリのデータを表示することを選択すると、Microsoft 365 システムは組織の使用状況履歴データの生成を開始します。 テナントのサイズによっては、この手順に 2 時間から 48 時間かかることがあります。 
  
 **これを修正するには、次の手順を実行します。** お待ちください。ただし、メッセージが 3日後にデータに変更されない場合は [、Microsoft 365](../contact-support-for-business-products.md)に問い合わせ、ビジネス サポートにお問い合わせください。
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>現在、リクエストを処理できません。 引き続き組織のデータを準備しています。

 **エラー コード:** 423 
  
 **このメッセージが表示される場所:** Power BI で、Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 レポート API を直接呼び出す場合。 
  
 **原因:** 管理センター [からテンプレート](enable-usage-analytics.md) アプリのデータを表示することを選択すると、Microsoft 365 システムは組織の使用状況履歴データの生成を開始します。 テナントのサイズに応じて、この手順は 2 時間から 48 時間の間の任意の場所で実行できます。 
  
 **これを修正するには、次の手順を実行します。** お待ちください。ただし、メッセージが開始から 3 日経ってもデータが変更されない場合は [、Microsoft 365 に](../contact-support-for-business-products.md)問い合わせ、ビジネス サポートにお問い合わせください。 
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>入力したテナント ID の形式が間違っています

 **エラー コード:** 400 
  
 **このメッセージが表示される場所:** Power BI で、Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 レポート API を直接呼び出す場合。 
  
 **原因:** テナント ID は guid であり、xxxxxxxx-xxxx-xxxx-xxxx-xxx の形式である必要があります。 テナント入力ボックスに他の文字列を入力すると、このエラーが発生します。 
  
 **このエラーを修正するには、次の手順を実行します。** 管理センターの [レポートの使用状況] に移動し、メイン ダッシュボード ページの \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>[Microsoft 365 利用状況分析] タイルを見つける。 テナント ID がタイルに一覧表示されます。 ここからコピーして、テンプレート アプリに接続するためのダイアログ ボックスに貼り付けます。 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>入力したテナント ID が弊社のシステムで認識されません

 **エラー コード:** 404 
  
 **このメッセージが表示される場所:** Power BI で Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 Reporting API を直接呼び出す場合。 
  
 **原因:** 指定したテナント ID が無効か、存在しません。 
  
 **このエラーを修正するには、次の手順を実行します。** 管理センターの [レポートの使用状況] に移動し、メイン ダッシュボード ページの \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>[Microsoft 365 利用状況分析] タイルを見つける。 テナント ID がタイルに一覧表示されます。 ここからコピーして、テンプレート アプリに接続するためのダイアログ ボックスに貼り付けます。 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>資格情報を再入力して Power BI にもう一度サインインしてください

エラー コード:302
  
 **このメッセージが表示される場所:** Power BI で Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 Reporting API を直接呼び出す場合。 
  
 **原因:** 認証コードが不合格となり、資格情報の再入力が求められている可能性があります。 
  
 **修正方法:** Power BI からサインアウトし、もう一度サインインします。 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>このデータにアクセスする権限がありません。 このサービスからデータにアクセスする権限を取得できるようにするには、グローバル管理者か、いずれかの製品管理者である必要があります。

 **エラー コード:** 403 
  
 **このメッセージが表示される場所:** Power BI で Microsoft 365 Usage Analytics テンプレート アプリに接続する場合、または Microsoft 365 Reporting API を直接呼び出す場合。 
  
 **原因:** テンプレート アプリに接続しようとしたユーザーが、このデータにアクセスするための適切なレベルの承認を持たないので、承認コードは失敗しました。 
  
 **このエラーを修正するには、次の手順を実行します。** グローバル管理者 **、Exchange** 管理者 **、Skype for Business** 管理者 **、SharePoint 管理者**、グローバル リーダー、またはレポートリーダーのいずれかであるユーザーの資格情報を入力して、テンプレート アプリに接続します。  詳細については [、「管理者ロールについて](../add-users/about-admin-roles.md) 」を参照してください。 
  
## <a name="refresh-failed"></a>更新が失敗しました

 **このメッセージが表示される場所:** Power BI からの電子メールまたは更新履歴の失敗した状態。 
  
 **原因:** テンプレート アプリに接続したユーザーの資格情報がリセットされ、テンプレート アプリの接続設定で更新されないと、更新エラーが表示される場合があります。 
  
 **このエラーを修正するには、次の手順を実行します。** Power BI で、Microsoft 365 Usage Analytics テンプレート アプリに対応するデータセットを検索し、[更新のスケジュール設定] を選択し、管理者資格情報を指定します。 
  
それでも問題が生じなかった場合は、キャッシュをクリアし、テンプレート アプリを再作成します。
  
  
