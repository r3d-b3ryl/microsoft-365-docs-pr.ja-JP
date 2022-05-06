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
| 1   | **Microsoft 365サポート** タブが表示されない                                                                                                                                                                                    | フィルター xmiomsm365assit\_\_ を使用して、現在のビューと **システム ログ** &gt; **をすべて** 確認する\_                        |
| 2   | **Microsoft 推奨ソリューション** を選択しますが、「ServiceNow 管理者にお問い合わせいただき、アプリのセットアップ手順を完了するように依頼してください」というエラーが表示されます。                                                                      | フォームの上部にあるエラー メッセージと、フィルター xmiomsm365assit\_\_\_ を使用して **システム ログ** &gt; **をすべて** 確認する     |
| 3   | **Microsoft 推奨ソリューション** を選択しますが、"ServiceNow 管理者に連絡し、アプリの最後のセットアップ 手順を完了するように依頼してください" というエラーが表示されます。                                                                | フォームの上部にあるエラー メッセージと、フィルター xmiomsm365assit\_\_\_ を使用して **システム ログ** &gt; **をすべて** 確認する     |
| 4   | 検索ボックスに問題を入力し、 **Microsoft 推奨ソリューション** を選択しますが、「ServiceNow 管理者にお問い合わせいただき、アプリのセットアップ手順を完了するように依頼してください」というエラーが表示されます。                                   | フォームの上部にあるエラー メッセージと、フィルター xmiomsm365assit\_\_\_ を使用して **システム ログ** &gt; **をすべて** 確認する     |
| 5   | 検索ボックスに問題を入力し、 **Microsoft 推奨ソリューション** を選択しますが、「ServiceNow 管理者に連絡し、アプリの最後のセットアップ手順を完了するように依頼してください」というエラーが表示されます。                                 | フォームの上部にあるエラー メッセージと、フィルター xmiomsm365assit\_\_\_ を使用して **システム ログ** &gt; **をすべて** 確認する     |
| 6    | **[Microsoft サポートにお問い合わせください**] を選択しますが、"ServiceNow 管理者にお問い合わせいただき、アプリのセットアップ手順を完了するように依頼してください" というエラーが表示されます。                                                                       | フォームの上部にあるエラー メッセージと、フィルター xmiomsm365assit\_\_\_ を使用して **システム ログ** &gt; **をすべて** 確認する     |
| 7    | **[Microsoft サポートにお問い合わせください**] を選択しますが、"ServiceNow 管理者に連絡し、アプリの最後のセットアップ 手順を完了するように依頼してください" というエラーが表示されます。                                                                 | フォームの上部にあるエラー メッセージと、フィルター xmiomsm365assit\_\_\_ を使用して **システム ログ** &gt; **をすべて** 確認する     |
| 8    | **[Microsoft サポートにお問い合わせください**] を選択しますが、"{EmailAddress} は有効なMicrosoft 365管理者アカウントではありません。 サービス要求を開くには、Microsoft 365管理者特権が必要です。 アプリで、管理者アカウントをリンクします。 | フォームの上部にあるエラー メッセージと、フィルター xmiomsm365assit\_\_\_ を使用して **システム ログ** &gt; **をすべて** 確認する     |
| 9    | **Microsoft 推奨ソリューション** を選択しますが、何も表示されません                                                                                                                                                            | **システム ログの確認 -** フィルター login.microsoftonline.com と connector.rave.microsoft.com を使用した送信 HTTP ログ |
| 10  | **Microsoft 推奨ソリューション** を選択しますが、"アプリ サポートにお問い合わせください" というエラーが表示されます。                                                                                                                                     | フォームの上部にあるエラー メッセージと、フィルター xmiomsm365assit\_\_\_ を使用して **システム ログ** &gt; **をすべて** 確認する     |
| 11  | 検索ボックスに問題を入力し、 **Microsoft 推奨ソリューション** を選択しますが、何も表示されない                                                                                                                             | **システム ログの確認 -** フィルター login.microsoftonline.com と connector.rave.microsoft.com を使用した送信 HTTP ログ |
| 12   | 検索ボックスに問題を入力し、 **Microsoft 推奨ソリューション** を選択しますが、"アプリ サポートにお問い合わせください" というエラーが表示されます。                                                                                                      | フォームの上部にあるエラー メッセージと、フィルター xmiomsm365assit\_\_\_ を使用して **システム ログ** &gt; **をすべて** 確認する     |
| 13  | ユーザーが **[Microsoft サポートに問い合わせる**] を選択しますが、何も起こりません                                                                                                                                                            | **システム ログの確認 -** フィルター login.microsoftonline.com と connector.rave.microsoft.com を使用した送信 HTTP ログ |
| 14  | インシデントを再度開いた後、Microsoft 推奨ソリューションが表示されない                                                                                                                                                      | フィルター xmiomsm365assit\_\_ で **システム ログ** &gt; **をすべて** 確認する\_                                              |
| 15  | Microsoft サポートに転送されたインシデントを再度開くときに Microsoft のケースが表示されない                                                                                                                            | フィルター xmiomsm365assit\_\_ で **システム ログ** &gt; **をすべて** 確認する\_                                              |
| 16  | チケットの詳細を保存できません。"チケットの詳細を保存できません。 App Support にお問い合わせください。                                                                                                                          | フォームの上部にあるエラー メッセージを確認する                                                                            |
