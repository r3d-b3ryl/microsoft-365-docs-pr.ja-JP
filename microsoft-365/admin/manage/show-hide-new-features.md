---
title: 新機能に表示されるOffice機能を管理する
f1.keywords:
- NOCSH
ms.author: danbrown
author: DHB-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 管理センターの [新機能] 機能を使用して、ユーザーがWindowsのOffice アプリで [ヘルプ] > [新機能] を選択したときに表示または非表示にする Office Office機能を決定します。
ms.openlocfilehash: 53372a4075de6d6a4790d49dc23e79e0ca60d65d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60155996"
---
# <a name="manage-which-office-features-appear-in-whats-new"></a>新機能に表示されるOffice機能を管理する

重要なOffice機能がリリースされると、WindowsのOffice アプリで [**ヘルプ**\>の **新機能**] を選択すると、その機能に関するメッセージが表示されます。

Microsoft 365 管理センターの [新機能] 機能を使用して、ユーザーに表示されるこれらの機能メッセージ **Office** 制御できます。 ユーザーに対して機能メッセージを非表示にすることにした場合は、いつでも後で戻って表示することができます。

> [!NOTE]
>
> - ユーザーからの機能メッセージを非表示にしても、Office アプリの機能は無効になりません。
> - [Officeの **新機能**] 機能を使用するには、グローバル管理者ロールまたはOffice アプリ管理者ロールのいずれかを割り当てる必要があります。

## <a name="show-or-hide-new-features"></a>新機能の表示と非表示を切り替える

1. Microsoft 365 管理センターの **[設定**] で [**組織の設定**] を選択し、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**サービス**] タブ</a>を選択し、[**Officeの新機能**] を選択します。
1. 機能名をクリックすると、ポップアップ パネルが表示され、次の情報が表示されます。
     - 機能の簡単な説明。
     - 機能の詳細を確認するための記事へのリンク。
     - 機能が表示されるOffice アプリケーション。
     - そのチャネルで機能を使用できる最初のバージョン (リリース)。
1. [ **ユーザーから非表示]** を選択します。 または、以前に機能を非表示にした場合は、[ **ユーザーに表示]** を選択します。

[新機能] ページに **表示される [管理] Office機能で複数の機能** を選択し、[**非表示]** または [**表示**] を選択することもできます。

> [!NOTE]
>
> - 複数のOffice アプリで機能を使用できる場合、機能を **[非表示]** に設定すると、それらのすべてのOffice アプリで機能メッセージが非表示になります。
> - 既定では、すべての機能メッセージがユーザーに表示されます。 これはすべての機能の既定の状態であり、機能メッセージを非表示または表示するように選択した場合にのみ状態が変更されます。
> - Microsoft 365 Apps管理センター (<https://config.office.com>) から **Office** 新機能にアクセスすることもできます。 この機能は、**CustomizationWhat** >  **の新しい管理の** 下にあります。

## <a name="list-of-features"></a>機能の一覧

[新機能] ページに表示 **される [管理] Office機能に表示される機能を** フィルター処理できます。 チャネル、アプリケーション、状態、またはそれらの組み合わせによってフィルター処理できます。

次のスケジュールに基づいて、ページに新機能が表示されます。

<br>

****

|チャネル|日付|アクションを行う|
|---|---|---|
|**Current**|月の 15 日|月次リリースの 1 ~ 3 週間前|
|**月次Enterprise**|月の最初|新機能をもたらすメジャー リリースの 2 週間前|
|**半期Enterprise (プレビュー)**|9 月 1 日と 3 月 1 日| 新機能をもたらすメジャー リリースの 2 週間前|
|**半期Enterprise**|1 月 1 日と 7 月 1 日| 新機能をもたらすメジャー リリースの 2 週間前|
|

新しいバージョンが各更新チャネルにリリースされるタイミングの詳細については、「[Microsoft 365 Appsの更新履歴 (日付別に一覧表示)」](/officeupdates/update-history-microsoft365-apps-by-date)を参照してください。

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>管理センターのホーム ページに [Officeの新機能] カードを追加する

1. Microsoft 365管理ページで、ページの上部にある [**カードの追加**] を選択します。
2. 一覧 **の [新機能] に表示される [管理] Office機能** を見つけて選択します。
3. カードがホーム ページに表示されたら、[**Officeの新機能**] を選択して、組織 [の機能を表示または非表示にすることができます](#show-or-hide-new-features)。

## <a name="related-articles"></a>関連記事

[Office 新機能の管理が一般公開されました](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)
