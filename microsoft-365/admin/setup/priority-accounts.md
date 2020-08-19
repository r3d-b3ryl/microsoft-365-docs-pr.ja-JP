---
title: 優先度アカウントを管理および監視する
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: ビジネスへの影響が大きいアカウントによって送受信された、失敗した電子メールメッセージと遅延した電子メールメッセージを監視します。
ms.openlocfilehash: 053246da7f57c46045bfc777bc4de981ce51c6e5
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794201"
---
# <a name="manage-and-monitor-priority-accounts"></a>優先度アカウントを管理および監視する

Microsoft 365 組織の管理者として、CEO のようなビジネスへの影響が大きいユーザーに送信された、失敗したまたは遅延した電子メールメッセージを監視できるようになりました。 この機能を有効にするには、優先度のアカウントの一覧にユーザーを追加します。 優先度のアカウントは、組織の実行に不可欠なアカウントです。 経営幹部、リーダー、マネージャー、または機密または高優先度の情報にアクセスできる他のユーザーを追加します。

## <a name="access-priority-accounts"></a>アクセス優先度のアカウント

このトピックに記載されている優先順位のアカウント機能は、次の両方の要件を満たす組織にのみ使用できます。

- Office 365 E3 または Microsoft 365 E3、あるいは Office 365 E5 または Microsoft 365 E5。
- 少なくとも1万のライセンスと、少なくとも50のアクティブな Exchange Online ユーザー。

## <a name="add-priority-accounts-from-the-setup-page"></a>セットアップページから優先度アカウントを追加する

[ **セットアップ] ページ**で、優先度の高いアカウントを追加します。

1. Microsoft 365 管理センター () に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。

2. [**セットアップ**  >  **の組織ナレッジ**] に移動して、[**最も重要なアカウントを監視**する] の下にある [**表示**] を選択します。

3. [ **開始** ] または [ **管理**] を選択します。

4. [ **優先度アカウントの追加** ] ページで、検索フィールドに、優先度アカウントリストに追加するユーザーの名前または電子メールアドレスを入力します。 また、失敗したメールまたは遅延したメールのメールのしきい値を設定して、優先度アカウントの問題の週単位のレポートを取得することもできます。

5. ユーザーを選択して、[ **保存**] を選択します。

[アクティブなユーザー] ページから優先度の高いアカウントを追加することもできます。

### <a name="add-priority-accounts-from-active-users-page"></a>[アクティブなユーザー] ページから優先度のアカウントを追加する

[アクティブなユーザー] ページから優先度の高いアカウントを追加します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。

2. [**ユーザー**の  >  **アクティブなユーザー**] に移動し、ページの上部にある [.. **.** ] を選択します。 [ **優先度アカウントの管理**] を選択します。

3. [ **アカウントの追加**] を選択し、[ **優先度アカウントの追加** ] ページの検索フィールドに、優先度のアカウント一覧に追加するユーザーの名前を入力します。

4. ユーザーを選択して、[ **保存**] を選択します。

## <a name="monitor-your-priority-accounts"></a>優先度の高いアカウントを監視する

[ **セットアップ** ] ページの Microsoft 365 管理センターで、優先度の高いアカウントの電子メールの状態を監視できます。 最大250のアカウントをアクティブに監視できます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。

2. [**セットアップ**] を選択し、[**プレミアム監視**] の横にある [**表示**] を選択して、優先度アカウントの状態を表示します。

## <a name="email-issues-for-priority-accounts"></a>優先度アカウントの電子メールの問題

優先度の高いアカウントの電子メールの問題を追跡するには、Exchange 管理センターで [ **優先度の高いアカウントの電子メールの問題点** レポートにアクセスします。 詳細については、「 [優先度のアカウントの電子メールの問題](https://review.docs.microsoft.com/en-us/Exchange/mail-flow-best-practices/mail-flow-insights/mfi-email-issues-for-priority-accounts?branch=Priority-chrisda)」をご覧ください。

## <a name="remove-a-user-from-the-priority-accounts-list"></a>優先順位のアカウントリストからユーザーを削除する

1. Microsoft 365 管理センター () に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。

2. [**セットアップ**  >  **の組織ナレッジ**] に移動して、[**最も重要なアカウントを監視**する] の下にある [**表示**] を選択します。

3. [**大部分のアカウントの監視**] ページで、[**この機能の管理**] の [**優先度の高いアカウント**] を選択します。

4. [ **優先度アカウント** ] ページで、リストから削除するユーザーを選択し、[ **アカウントの削除**] を選択します。