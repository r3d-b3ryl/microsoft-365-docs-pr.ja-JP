---
title: 使用状況分析Microsoft 365トラブルシューティング
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: 使用状況分析テンプレート アプリに関する問題のトラブルシューティングMicrosoft 365説明します。
ms.openlocfilehash: b13ec0338c6ad48a5f5006528d77fbbdc290e7f5
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774354"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>使用状況分析Microsoft 365トラブルシューティング

次のエラー メッセージの一覧を参照して、使用状況分析に関する最も一般的な問題Microsoft 365確認してください。
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>リクエストを処理できません。 最初に、このデータを登録する必要Microsoft 365 管理センター

 **エラー コード:** 422 
  
 **このメッセージが表示される場所:** このPower BI Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出す場合Microsoft 365です。 
  
 **原因:** アプリに接続する前に、アプリからデータをサブスクライブするMicrosoft 365 管理センター。 この手順を最初に行わなくても、テナント ID を指定した場合でも、テンプレート アプリMicrosoft 365できません。 
  
 **このエラーを修正するには、次の手順を実行します。** データをサブスクライブするには、管理センターの [レポートの使用状況] に移動し、メイン ダッシュボード ページで [Microsoft 365利用状況分析 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>] タイルを探します。 [作業の **開始]** ボタンを選択し、開く [レポート] ウィンドウで、[データの使用状況分析でデータを使用Microsoft 365する] Power BIをオンにし、[保存]**を****オンにします**。
  
## <a name="we-are-processing-your-data"></a>データを処理しています

 **このメッセージが表示される場所:**[使用状況 **Microsoft 365] タイルの**[使用状況]ダッシュボードの [Microsoft 365 管理センター。 
  
 **原因:** テンプレート アプリ [内の](enable-usage-analytics.md)データを Microsoft 365 管理センター から表示することを選択すると、Microsoft 365 システムは組織の使用状況履歴データの生成を開始します。 テナントのサイズによっては、この手順に 2 時間から 48 時間かかることがあります。 
  
 **これを修正するには、次の手順を実行します。** お待ちください。ただし、メッセージが 3日後にデータに変更されない場合は、Microsoft 365 [に問い合わせください](../../business-video/get-help-support.md)。
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>現在、リクエストを処理できません。引き続き組織のデータを準備しています。

 **エラー コード:** 423 
  
 **このメッセージが表示される場所:** このPower BI、 Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出Microsoft 365場合。 
  
 **原因:** 管理センター [からテンプレート](enable-usage-analytics.md)アプリのデータを表示することを選択すると、Microsoft 365システムは組織の使用状況履歴データの生成を開始します。 テナントのサイズに応じて、この手順は 2 時間から 48 時間の間の任意の場所で実行できます。 
  
 **これを修正するには、次の手順を実行します。** お待ちください。ただし、メッセージが開始から 3 日経ってもデータが変更されない場合は、ビジネス サポートMicrosoft 365 [問い合わせください](../../business-video/get-help-support.md)。 
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>入力したテナント ID の形式が間違っています

 **エラー コード:** 400 
  
 **このメッセージが表示される場所:** このPower BI、 Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出Microsoft 365場合。 
  
 **原因:** テナント ID は guid であり、xxxxxxxx-xxxx-xxxx-xxxx-xxx の形式である必要があります。 テナント入力ボックスに他の文字列を入力すると、このエラーが発生します。 
  
 **このエラーを修正するには、次の手順を実行します。** 管理センターの [レポートの使用状況] に移動し、メイン ダッシュボード Microsoft 365の [使用状況分析 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>] タイルを探します。 テナント ID がタイルに一覧表示されます。 ここからコピーして、テンプレート アプリに接続するためのダイアログ ボックスに貼り付けます。 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>入力したテナント ID が弊社のシステムで認識されません

 **エラー コード:** 404 
  
 **このメッセージが表示される場所:** このPower BI Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出す場合Microsoft 365です。 
  
 **原因:** 指定したテナント ID が無効か、存在しません。 
  
 **このエラーを修正するには、次の手順を実行します。** 管理センターの [レポートの使用状況] に移動し、メイン ダッシュボード Microsoft 365の [使用状況分析 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>] タイルを探します。 テナント ID がタイルに一覧表示されます。 ここからコピーして、テンプレート アプリに接続するためのダイアログ ボックスに貼り付けます。 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>資格情報を再入力して Power BI にもう一度サインインしてください

エラー コード:302
  
 **このメッセージが表示される場所:** このPower BI Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出す場合Microsoft 365です。 
  
 **原因:** 認証コードが不合格となり、資格情報の再入力が求められている可能性があります。 
  
 **修正方法:** Power BI からサインアウトし、もう一度サインインします。 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>このデータにアクセスする権限がありません。このサービスからデータにアクセスする権限を取得できるようにするには、グローバル管理者か、いずれかの製品管理者である必要があります。

 **エラー コード:** 403 
  
 **このメッセージが表示される場所:** このPower BI Usage Analytics テンプレート アプリに接続する場合、Microsoft 365レポート API を直接呼び出す場合Microsoft 365です。 
  
 **原因:** テンプレート アプリに接続しようとしたユーザーが、このデータにアクセスするための適切なレベルの承認を持たないので、承認コードは失敗しました。 
  
 **このエラーを修正するには、次の手順を実行します。** グローバル管理者 **、Exchange 管理者、Skype for Business** **管理者、SharePoint** 管理者、グローバル リーダー、レポート リーダーのいずれかであるユーザーの資格情報を入力して、テンプレート アプリに接続します。 詳細については [、「管理者ロールについて](../add-users/about-admin-roles.md) 」を参照してください。 
  
## <a name="refresh-failed"></a>更新が失敗しました

 **このメッセージが表示される場所:** Power BI からの電子メールまたは更新履歴の失敗した状態。 
  
 **原因:** テンプレート アプリに接続したユーザーの資格情報がリセットされ、テンプレート アプリの接続設定で更新されないと、更新エラーが表示される場合があります。 
  
 **このエラーを修正するには、次の手順を実行します。**[Power BI、 Usage Analytics テンプレート アプリに対応するデータセットをMicrosoft 365更新のスケジュールを選択し、管理者資格情報を指定します。 
  
それでも問題が生じなかった場合は、キャッシュをクリアし、テンプレート アプリを再作成します。
  
  
