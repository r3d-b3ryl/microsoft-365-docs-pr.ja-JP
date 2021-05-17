---
title: 新機能にOffice機能を管理する
f1.keywords:
- NOCSH
ms.author: danbrown
author: DHB-MSFT
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
description: Microsoft 365 管理センターの > [Office の新機能] 機能を使用して、ユーザーが Office アプリ の Office アプリ on Windows で [新機能] を選択した場合に表示または非表示にする Office 機能を決定します。
ms.openlocfilehash: b9d20e3df4a2de540316dce0e6a6905c07e65176
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915029"
---
# <a name="manage-which-office-features-appear-in-whats-new"></a>新機能にOffice機能を管理する

重要なOffice機能がリリースされると、ユーザーはアプリの [ヘルプの新機能] を選択すると、その機能に関するOffice  >  をWindows。

ユーザーが表示するこれらの機能メッセージを制御するには、管理センターの[Officeの新機能Microsoft 365使用します。 ユーザーに対して機能メッセージを非表示にした場合は、後でいつでも戻ってきて、ユーザーに表示することができます。

> [!NOTE]
> - ユーザーから機能メッセージを非表示にしても、ユーザーの機能が無効Office アプリ。
> - [新しい機能] 機能を使用するには、グローバル管理者ロールまたは Office アプリ管理者ロールのいずれかを割り **当てるOffice** があります。

## <a name="show-or-hide-new-features"></a>新機能の表示と非表示を切り替える 

1. 管理センターの [Microsoft 365] で、[**組織** 設定]**を選択します**。
2. [サービス **] タブで**、[サービスの新機能] を選択 **Office。**
3. 機能名をクリックすると、フライアウト パネルが表示され、次の情報が表示されます。
     - 機能の簡単な説明。
     - 機能の詳細については、記事へのリンクを参照してください。
     - このOffice表示されるアプリケーションの一部です。
     - この機能がチャネルで使用できる最初のバージョン (リリース) です。
4. [ユーザー **から非表示にする] を選択します**。 または、以前に機能を非表示にした場合は、[ユーザーに **表示] を選択します**。

[新機能] ページに表示Office機能の管理] で複数の機能を選択し、[非表示] または [表示]**を** 選択 **することもできます**。

> [!NOTE]
> - 複数のアプリで機能を使用できるOffice機能を [非表示] に設定すると、これらのアプリのすべての機能メッセージOfficeされます。
> - すべての機能メッセージは、既定でユーザーに表示されます。 これはすべての機能の既定の状態であり、機能メッセージの非表示または表示を選択した場合にのみ状態が変更されます。
> - また、管理センター **()** から[Officeの新機能Microsoft 365 Apps取得できます [https://config.office.com](https://config.office.com) 。 この機能は、カスタマイズ **の**  >  **[新しい管理] の下に表示されます**。

## <a name="list-of-features"></a>機能の一覧

[新しい機能の管理] ページに表示Office **機能をフィルター処理** できます。 チャネル、アプリケーション、または状態、またはこれらの組み合わせによってフィルター処理できます。

新しい機能は、次のスケジュールに基づいてページに表示されます。

||||
|:-----|:-----|:-----|
|**チャネル** <br/> |**Date** <br/> |**アクションを行う** <br/> |
|**Current** <br/> |月の 15 日  <br/> |月次リリースの 1 ~ 3 週間前 <br/> |
|**月次Enterprise** <br/> |月の最初  <br/> |新機能をもたらすメジャー リリースの 2 週間前 |
|**半期のEnterprise (プレビュー)** <br/> |9 月 1 日と 3 月 1 日 <br/> | 新機能をもたらすメジャー リリースの 2 週間前|
|**半期のEnterprise** <br/> |1 月 1 日と 7 月 1 日 <br/> | 新機能をもたらすメジャー リリースの 2 週間前<br/> |

新しいバージョンが各更新プログラム チャネルにリリースされる時期の詳細については、「更新プログラムの更新履歴 (日付Microsoft 365 Apps一覧)」を[参照してください](/officeupdates/update-history-microsoft365-apps-by-date)。

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>管理センターのホーム ページに "Officeの新機能" カードを追加する

1. [管理者Microsoft 365] ページで、ページ **の上部にある**[カードの追加] を選択します。
2. [**検索] リストOffice新機能に** 表示される機能を管理し、選択します。
3. カードがホーム ページに表示された後、組織の機能を表示または非表示Officeの新機能を選択[](#show-or-hide-new-features)できます。


## <a name="related-articles"></a>関連記事

[Office新機能の管理が一般に利用可能に](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)