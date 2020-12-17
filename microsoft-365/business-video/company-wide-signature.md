---
title: 会社全体の署名を作成する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 会社全体の電子メール署名を作成する方法について学習します。
ms.openlocfilehash: 64c269abd25cab74ec5b0836975902e46a611c8c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703032"
---
# <a name="create-a-company-wide-email-signature"></a>会社全体の電子メール署名を作成する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

会社全体の電子メール署名は、組織内のユーザーによって送信される電子メールごとに表示されます。 会社の連絡先情報や法的免責事項など、重要な詳細を表示するために使用できます。 

## <a name="try-it"></a>演習

1. Microsoft 365 管理センターで **、[Exchange]** を選択します。
1. [メール **フロー] を選択します**。
1. [ **追加 +] を選択** し、[免責事項の適用 **] を選択します**。
1. [新しい **ルール] ページで、次の設定を** 行います。
    1. ルールの名前を入力します。
    1. From the **Apply this rule if** drop-down list, select Apply to all **messages**.
    1. [実行 **する操作] ドロップダウン** リストで、免責事項の **追加が表示されるのを** 確認します。
    1. ページの右側で [テキストの入力] を選択し、[免責事項の指定] テキスト ボックスに電子メール署名のテキスト **を** 入力します。 HTML でテキストを書式設定することで、署名の外観を向上できます。
    1. 署名に画像を表示する場合は、その画像に公開されている URL を使用する必要があります。 Web 上のイメージを参照し、右クリックして、[イメージ アドレスのコピー **] を選択します**。 [免責事項の指定] テキスト **ボックスにアドレスを** 貼り付けます。 **[OK] を** 選択し、下にスクロールします。
    1. 署名が暗号化された電子メールで機能するには、フォールバック オプションを追加します。 On the right of the page, choose **Select one,** choose **Wrap,** and then select **OK**.
    1. 下にスクロールし、モードを[強制] のままにして、[保存] を選択 **します**。
1. 警告メッセージが表示されます。 今後 **のすべてのメッセージに** ルールを適用するには、[はい] を選択します。

    署名が作成されました。 次のメールを送信すると、作成した署名は表示されませんが、メールの受信者には表示されます。