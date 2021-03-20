---
title: Manage which ‎Office‎ features appear in What's New
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
description: Microsoft 365 管理センターの 「Office の新機能」機能を使用して、ユーザーが Windows 上の Office アプリで [ヘルプ> 新機能] を選択した場合に表示または非表示にする Office 機能を決定します。
ms.openlocfilehash: b9d20e3df4a2de540316dce0e6a6905c07e65176
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915029"
---
# <a name="manage-which-office-features-appear-in-whats-new"></a>Manage which Office‎ features appear in What's New

When an important ‎Office‎ feature is released, users will get a message about it when they choose **Help**  >  **What's New** in their ‎‎Office‎‎ app on ‎Windows‎.

Microsoft 365 管理センターの [新しい機能] 機能を使用して、ユーザーに表示される **Office** を制御できます。 ユーザーに対して機能メッセージを非表示にした場合は、後でいつでも戻ってきて、ユーザーに表示することができます。

> [!NOTE]
> - ユーザーから機能メッセージを非表示にしても、アプリ内の機能はOfficeされません。
> - [新しい機能] 機能を使用するには、グローバル管理者ロールまたは Office アプリ管理者ロールのいずれかを割り **当Office** があります。

## <a name="show-or-hide-new-features"></a>新機能の表示と非表示を切り替える 

1. Microsoft 365 管理センターの [設定] で **、[組織の** 設定] **を選択します**。
2. [サービス **] タブで**、[サービスの新機能] を選択 **Office。**
3. 機能名をクリックすると、フライアウト パネルが表示され、次の情報が表示されます。
     - 機能の簡単な説明。
     - 機能の詳細については、記事へのリンクを参照してください。
     - このOffice表示されるアプリケーションの一部です。
     - この機能がチャネルで使用できる最初のバージョン (リリース) です。
4. [ユーザー **から非表示にする] を選択します**。 または、以前に機能を非表示にした場合は、[ユーザーに **表示] を選択します**。

You can also select multiple features on the **Manage which ‎Office‎ features appear in What's New** page, and then choose either **Hide** or **Show**.

> [!NOTE]
> - 複数のアプリで機能を使用できるOffice機能を [非表示]に設定すると、これらのアプリのすべての機能メッセージOfficeされます。
> - すべての機能メッセージは、既定でユーザーに表示されます。 これはすべての機能の既定の状態であり、機能メッセージの非表示または表示を選択した場合にのみ状態が変更されます。
> - また、Microsoft 365 Apps 管理センター **()** Office機能の新機能にアクセスすることもできます [https://config.office.com](https://config.office.com) 。 この機能は、カスタマイズ **の**  >  **[新しい管理] の下に表示されます**。

## <a name="list-of-features"></a>機能の一覧

You can filter which features appear on the **Manage which ‎Office‎ features appear in What's New** page. チャネル、アプリケーション、または状態、またはこれらの組み合わせによってフィルター処理できます。

新しい機能は、次のスケジュールに基づいてページに表示されます。

||||
|:-----|:-----|:-----|
|**チャネル** <br/> |**日付** <br/> |**アクションを行う** <br/> |
|**Current** <br/> |月の 15 日  <br/> |月次リリースの 1 ~ 3 週間前 <br/> |
|**月次エンタープライズ** <br/> |月の最初  <br/> |新機能をもたらすメジャー リリースの 2 週間前 |
|**半期エンタープライズ (プレビュー)** <br/> |9 月 1 日と 3 月 1 日 <br/> | 新機能をもたらすメジャー リリースの 2 週間前|
|**半期エンタープライズ** <br/> |1 月 1 日と 7 月 1 日 <br/> | 新機能をもたらすメジャー リリースの 2 週間前<br/> |

新しいバージョンが各更新プログラム チャネルにリリースされる時期の詳細については [、「Microsoft 365 Apps](/officeupdates/update-history-microsoft365-apps-by-date)の更新履歴 (日付別に一覧表示)」を参照してください。

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>管理センターのホーム ページに "Officeの新機能" カードを追加する

1. [Microsoft 365 管理] ページで、ページ **の上部にある [** カードの追加] を選択します。
2. [ **リストの新機能Office機能** を管理する] を見つけて選択します。
3. カードがホーム ページに表示された後、組織の機能を表示または非表示Officeの新機能を選択[](#show-or-hide-new-features)できます。


## <a name="related-articles"></a>関連記事

[Office新機能の管理が一般に利用可能に](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)