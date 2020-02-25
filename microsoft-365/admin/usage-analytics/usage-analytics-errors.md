---
title: Microsoft 365 usage analytics のトラブルシューティング
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Microsoft 365 Usage Analytics テンプレートアプリの問題をトラブルシューティングする方法について説明します。
ms.openlocfilehash: a9da79a6d7760f7876de7a6321554545d411f6be
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248186"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Microsoft 365 usage analytics のトラブルシューティング

次のエラーメッセージの一覧を参照して、Microsoft 365 usage analytics の一般的な問題に関するヘルプを取得します。
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>リクエストを処理できません。 最初に、Microsoft 365 管理センターからこのデータを購読する必要があります。

 **エラー コード:** 422 
  
 **このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。 
  
 **原因:** アプリに接続するには、Microsoft 365 管理センターからデータを購読する必要があります。 この手順を最初に実行しないと、Microsoft 365 テナント id を提供している場合でも、テンプレートアプリに接続できなくなります。 
  
 **このエラーを解決するには、次のようにします。** データをサブスクライブするには、 \>管理センターの [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">利用状況]</a> **レポート** \>を開き、ダッシュボードのメインページで Microsoft 365 Usage analytics タイルを探します。 [**作業の開始**] ボタンを選択し、開いた [**レポート**] ウィンドウで、[ **Power BI のための Microsoft 365 usage analytics のためにデータを利用できるようにする**] 設定をオンにして、[**保存**] をオンにします。
  
## <a name="we-are-processing-your-data"></a>データを処理しています

 **このメッセージが表示される場所は次のとおりです。** Microsoft 365 管理センターの**利用状況**ダッシュボードの**microsoft 365 usage analytics**タイル。 
  
 **原因:** Microsoft 365 管理センターから[テンプレートアプリのデータを表示することを選択](enable-usage-analytics.md)すると、microsoft 365 システムは組織の利用状況データの履歴を生成し始めます。 テナントのサイズによっては、この手順に 2 時間から 48 時間かかることがあります。 
  
 **この問題を解決するには**しばらくお待ちくださいが、メッセージが3日後に**データ**に変更されない場合は、 [Microsoft 365 for business サポートにお問い合わせください](../contact-support-for-business-products.md)。
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>現在、リクエストを処理できません。 引き続き組織のデータを準備しています。

 **エラー コード:** 423 
  
 **このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。 
  
 **原因:** 管理センターから[テンプレートアプリのデータを表示することを選択](enable-usage-analytics.md)すると、Microsoft 365 システムによって、組織の利用状況データの履歴生成が開始されます。 テナントのサイズによっては、この手順に 2 時間から 48 時間かかることがあります。 
  
 **この問題を解決するには**しばらくお待ちくださいが、**データの準備が完了**してから3日経っても、メッセージが変更されない場合は、 [Microsoft 365 for business サポートにお問い合わせください](../contact-support-for-business-products.md)。
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>入力したテナント ID の形式が間違っています

 **エラー コード:** 400 
  
 **このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。 
  
 **原因:** テナント ID は GUID であり、その形式は xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx にする必要があります。テナント入力ボックスに他の文字列を入力すると、このエラーが表示されます。 
  
 **このエラーを解決するには、次のようにします。** 管理センター \>の**レポート** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用法</a>に移動し、ダッシュボードのメインページで Microsoft 365 Usage analytics タイルを探します。 The tenant id is listed on the tile. ここからコピーして、テンプレートアプリに接続するためのダイアログボックスに貼り付けることができます。 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>入力したテナント ID が弊社のシステムで認識されません

 **エラー コード:** 404 
  
 **このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。 
  
 **原因:** 入力したテナント ID が無効であるか、存在しません。 
  
 **このエラーを解決するには、次のようにします。** 管理センター \>の**レポート** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用法</a>に移動し、ダッシュボードのメインページで Microsoft 365 Usage analytics タイルを探します。 The tenant id is listed on the tile. ここからコピーして、テンプレートアプリに接続するためのダイアログボックスに貼り付けることができます。 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>資格情報を再入力して Power BI にもう一度サインインしてください

エラー コード:302
  
 **このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。 
  
 **原因:** 認証コードが不合格となり、資格情報の再入力が求められている可能性があります。 
  
 **修正方法:** Power BI からサインアウトし、もう一度サインインします。 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>このデータにアクセスする権限がありません。 このサービスからデータにアクセスする権限を取得できるようにするには、グローバル管理者か、いずれかの製品管理者である必要があります。

 **エラー コード:** 403 
  
 **このメッセージが表示される場所は次のとおりです。** Power BI では、Microsoft 365 Usage Analytics テンプレートアプリに接続している場合、または Microsoft 365 レポート Api を直接呼び出している場合。 
  
 **原因:** テンプレートアプリに接続しようとしたユーザーがこのデータにアクセスするための適切な承認レベルを持っていないため、認証コードが失敗しました。 
  
 **このエラーを解決するには、次のようにします。****グローバル管理者**、 **Exchange 管理**者、 **Skype for business 管理者**、 **SharePoint 管理者**、**グローバルリーダ**、または**レポート**アプリに接続するユーザーの資格情報を指定します。 詳細については、「[管理者ロールについ](../add-users/about-admin-roles.md)て」を参照してください。 
  
## <a name="refresh-failed"></a>更新が失敗しました

 **このメッセージが表示される場所:** Power BI からの電子メールまたは更新履歴の失敗した状態。 
  
 **原因:** テンプレートアプリに接続したユーザーの資格情報がリセットされる場合があり、テンプレートアプリの接続設定で更新されていないと、ユーザーが更新エラーエラーを表示することがあります。 
  
 **このエラーを解決するには、次のようにします。** Power BI で、Microsoft 365 Usage Analytics テンプレートアプリに対応するデータセットを見つけ、[**更新のスケジュール**] を選択して、管理者の資格情報を入力します。 
  
それでもうまくいかない場合は、キャッシュをクリアし、テンプレートアプリを再作成します。
  
  
