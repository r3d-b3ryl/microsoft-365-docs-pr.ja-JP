---
title: ServiceNow との Microsoft 365 サポート統合のトラブルシューティング
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow のスコープ認定アプリケーションのインストールと構成ガイド。
ms.openlocfilehash: bac3981b728ac997839e7ac99a9411a8da244add
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63324943"
---
# <a name="troubleshooting-microsoft-365-support-integration-with-servicenow"></a>ServiceNow との Microsoft 365 サポート統合のトラブルシューティング

| \#  | 問題  | 診断アクション     |
|-----|--------------------------------|----------------------|
| 1   | [サポート] タブ **Microsoft 365表示** できない                                                                                                                                                                                    |  &gt;フィルター xmiomsm365assit\_\_ を使用して、現在のビューとシステム ログすべてを\_確認する                        |
| 2   | [ **Microsoft 推奨ソリューション]** を選択しますが、「ServiceNow 管理者に問い合わせ、アプリのセットアップ手順を完了してください」というエラーが表示されます。                                                                      | フォームの上部にあるエラー メッセージと&gt;、フィルター xmiomsm365assit\_\_ を使用してシステム ログすべてを\_確認する     |
| 3   | [ **Microsoft 推奨ソリューション]** を選択しますが、「ServiceNow 管理者に問い合わせ、アプリの最終的なセットアップ 手順を完了してください」というエラーが表示されます。                                                                | フォームの上部にあるエラー メッセージと&gt;、フィルター xmiomsm365assit\_\_ を使用してシステム ログすべてを\_確認する     |
| 4   | 検索ボックスに問題を入力し、[ **Microsoft** 推奨ソリューション] を選択しますが、「ServiceNow 管理者に問い合わせ、アプリのセットアップ手順を完了してください」というエラーが表示されます。                                   | フォームの上部にあるエラー メッセージと&gt;、フィルター xmiomsm365assit\_\_ を使用してシステム ログすべてを\_確認する     |
| 5   | 検索ボックスに「問題」と入力し、[ **Microsoft** 推奨ソリューション] を選択しますが、「ServiceNow 管理者に問い合わせ、アプリの最終的なセットアップ 手順を完了してください」というエラーが表示されます。                                 | フォームの上部にあるエラー メッセージと&gt;、フィルター xmiomsm365assit\_\_ を使用してシステム ログすべてを\_確認する     |
| 6    | [ **Microsoft サポートに問い合** わせ] を選択しますが、「ServiceNow 管理者に問い合わせ、アプリのセットアップ手順を完了してください」というエラーが表示されます。                                                                       | フォームの上部にあるエラー メッセージと&gt;、フィルター xmiomsm365assit\_\_ を使用してシステム ログすべてを\_確認する     |
| 7    | [ **Microsoft サポートに問** い合わせ] を選択しますが、「ServiceNow 管理者に問い合わせ、アプリの最終的なセットアップ 手順を完了してください」というエラーが表示されます。                                                                 | フォームの上部にあるエラー メッセージと&gt;、フィルター xmiomsm365assit\_\_ を使用してシステム ログすべてを\_確認する     |
| 8    | [**Microsoft サポートに問い合** わせ] を選択しますが、"{EmailAddress} は管理者アカウントMicrosoft 365取得します。 サービス要求をMicrosoft 365には、管理者特権が必要です。 アプリで、管理者アカウントをリンクします。 | フォームの上部にあるエラー メッセージと&gt;、フィルター xmiomsm365assit\_\_ を使用してシステム ログすべてを\_確認する     |
| 9    | Microsoft 推奨 **ソリューションを選択します** が、何も表示されません                                                                                                                                                            | [ **システム ログの確認] – フィルター処理とフィルター処理** を使用 login.microsoftonline.com HTTP ログ connector.rave.microsoft.com |
| 10  | [ **Microsoft 推奨ソリューション] を選択** しますが、「アプリのサポートに問い合わせください」というエラーが表示されます。                                                                                                                                     | フォームの上部にあるエラー メッセージと&gt;、フィルター xmiomsm365assit\_\_ を使用してシステム ログすべてを\_確認する     |
| 11  | 検索ボックスに問題を入力し、[Microsoft 推奨ソリューション] **を選択します** が、何も表示されません                                                                                                                             | [ **システム ログの確認] – フィルター処理とフィルター処理** を使用 login.microsoftonline.com HTTP ログ connector.rave.microsoft.com |
| 12   | 検索ボックスに「問題」と入力し、[ **Microsoft 推奨** ソリューション] を選択しますが、「アプリのサポートに問い合わせください」というエラーが表示されます。                                                                                                      | フォームの上部にあるエラー メッセージと&gt;、フィルター xmiomsm365assit\_\_ を使用してシステム ログすべてを\_確認する     |
| 13  | ユーザーが [ **Microsoft サポートに問い合わせ] を** 選択したが、何も起こらない                                                                                                                                                            | [ **システム ログの確認] – フィルター処理とフィルター処理** を使用 login.microsoftonline.com HTTP ログ connector.rave.microsoft.com |
| 14   | インシデントを再度開いた後に Microsoft 推奨ソリューションを表示できない                                                                                                                                                      | システム **ログすべてフィルター** &gt; xmiomsm365assit \_\_で\_確認する                                              |
| 15   | Microsoft サポートに転送されたインシデントを再度開くと、Microsoft ケースが表示されません                                                                                                                            | システム **ログすべてフィルター** &gt; xmiomsm365assit \_\_で\_確認する                                              |
| 16  | チケットの詳細を保存できません。エラー "チケットの詳細を保存できません。 アプリのサポートにお問い合わせください。                                                                                                                          | フォームの上部にあるエラー メッセージを確認する                                                                            |
