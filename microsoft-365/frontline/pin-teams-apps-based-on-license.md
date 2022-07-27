---
title: 現場担当者向けに Teams アプリを調整する
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Microsoft Teams の現場担当者向けにカスタマイズされたアプリ エクスペリエンスについて説明します。
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 24393b11abc9bb7ba4c6736daca4dfa5969f94b8
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66994889"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>現場担当者向けに Teams アプリを調整する

> [!NOTE]
> 現在ロールアウトされている最中で、お客様の組織ではまだ利用できない可能性があります。 Teams 機能の最新情報を入手するには、「[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)」を参照してください。

## <a name="overview"></a>概要

Teams では、ライセンスに基づいてアプリをピン留めし、現場のワーカーにニーズに合わせてカスタマイズされた Teams のすぐに使えるエクスペリエンスを提供します。 

現場担当者は、カスタマイズされた現場アプリ エクスペリエンスを使用して、管理者から何のアクションも必要とせずに、Teams で最も関連性の高いアプリを入手できます。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VuCH]

## <a name="tailored-frontline-app-experience"></a>カスタマイズされた現場アプリ エクスペリエンス

アプリは、アプリ バーにピン留めされます。このバーは、Teams モバイル クライアント (iOS および Android) の下側と Teams デスクトップ クライアントの横に表示されます。 次のアプリは、[F ライセンス](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)を持つユーザーに対してピン留めされます。

- [アクティビティ](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [チャット](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [ウォーキー トーキー](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [タスク](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Shifts](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [承認](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams モバイル**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="Teams モバイルでの調整された現場アプリ エクスペリエンス" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams デスクトップ**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="Teams デスクトップでの調整された現場アプリ エクスペリエンス" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>管理制御

> [!NOTE]
> この機能を有効にするには、**ユーザー ピン留め** 設定をグローバル (組織全体の既定値) の [アプリ設定ポリシー](/microsoftteams/teams-app-setup-policies)で有効にする必要があります。

調整された現場アプリ エクスペリエンスは、Teams 管理センターの [[アプリの管理]](/microsoftteams/manage-apps#manage-org-wide-app-settings) ページにある **[カスタマイズされたアプリの表示]** で組織全体のアプリ設定によって制御されます。 機能がオンの場合、F ライセンスを持つ組織内のすべてのユーザーが、カスタマイズされたアプリ エクスペリエンスを取得します。

ユーザーに割り当てられたカスタム [アプリ セットアップ ポリシー](/microsoftteams/teams-app-setup-policies)が優先されます。 つまり、ユーザーにカスタム アプリ セットアップ ポリシーが既に割り当てられている場合、ユーザーはカスタム アプリセットアップ ポリシーで定義されている構成を取得します。 グローバル アプリ設定ポリシーを含む Teams アプリ ポリシーで機能がどのように機能するかの詳細については、この記事で後述する[シナリオ](#scenarios) セクションを参照してください。

この機能は既定でオンになっています。 ただし、Microsoft が提供するカスタマイズされた現場アプリ エクスペリエンスが必要ない場合は、この機能をオフにすることができます。 機能をオフまたはオンにするには:

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリの管理]** に移動します。その後、**[組織全体のアプリ設定]** を選択します。
2. **[カスタマイズされたアプリ]** で、 **[カスタマイズされたアプリの表示]** を **オフ** または **オン** に切り替えます。

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Teams 管理センターの [アプリの管理] ページの [カスタマイズしたアプリの表示] 設定のを示すスクリーンショット" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>シナリオ

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>カスタマイズされた現場アプリ エクスペリエンスは、グローバル アプリのセットアップ ポリシーにどのように影響しますか?

カスタマイズされた現場アプリ エクスペリエンスがグローバル アプリのセットアップ ポリシーと連携するしくみについて説明します。 この表のシナリオは、F ライセンスとグローバル アプリセットアップ ポリシーを持つ現場担当者に適用され、**[ユーザー ピン留め]** がオンになっています。

|条件... |その後... |
|---------|---------|
|現場担当者にはグローバル アプリのセットアップ ポリシーがあり、この機能はオフになっています。 |現場担当者は、グローバル アプリのセットアップ ポリシーで定義されているアプリを取得します。|
|現場担当者にはグローバル アプリのセットアップ ポリシーがあり、この機能はオンになっています。     | 現場担当者は、カスタマイズされた現場アプリ エクスペリエンスを取得します。 グローバル アプリ セットアップ ポリシーで定義されたアプリは、カスタマイズされたアプリの下にピン留めされます。      |
|グローバル アプリのセットアップ ポリシーを更新すると、機能が有効になります。     |現場担当者は、カスタマイズされた現場のアプリ エクスペリエンスを取得し、グローバル アプリのセットアップ ポリシーで定義されているアプリは、カスタマイズされたアプリの下にピン留めされます。         |
|現場担当者にはグローバル アプリのセットアップ ポリシーがあり、**[ユーザー ピン留め]** がオフになっています。 |現場担当者は、グローバル アプリのセットアップ ポリシーで定義されているアプリを取得します。|
|現場担当者にはグローバル アプリのセットアップ ポリシーがあり、グローバル アプリのセットアップ ポリシーが変更され、アプリの一覧の 2 番目の位置に基幹業務 (LOB) アプリが含まれます。 |LOB アプリは、カスタマイズされたアプリの下にピン留めされます。 現場担当者は、**[ユーザー ピン留め]** がオンの場合、アプリの順序を変更できます。         |
|現場担当者にはグローバル セットアップ ポリシーがあり、グローバル アプリのセットアップ ポリシーが変更され、最初の位置に [シフト] が含まれるようになりました。  |シフトは、調整された現場アプリ エクスペリエンスで定義されているように、6 番目の位置にピン留めされます。 現場担当者は、**[ユーザー ピン留め]** がオンの場合、アプリの順序を変更できます。          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>カスタマイズされた現場アプリ エクスペリエンスは、他の Teams アプリ ポリシーとどのように連携しますか?

カスタマイズされた現場アプリ エクスペリエンスが他の Teams アプリ ポリシーとどのように連携するかについて説明します。

|条件...  |その後... |
|---------|---------|
この機能はオフです。   | 現場担当者は、グローバル アプリ セットアップ ポリシーまたは割り当てられたカスタム アプリ セットアップ ポリシーで定義されているアプリを取得します。          |
|現場担当者にはカスタム アプリのセットアップ ポリシーがあり、この機能はオンになっています。    |現場担当者は、カスタム アプリセットアップ ポリシーで定義されたアプリを取得します。          |
|カスタマイズされた現場アプリ エクスペリエンスのアプリは、ユーザーまたは組織に対してブロックされます。      |調整された現場アプリ エクスペリエンスは、[[アプリ アクセス許可ポリシー]](/microsoftteams/teams-app-permission-policies) に従います。 アプリがブロックされている場合、現場担当者にはブロックされたアプリは表示されません。           |
|カスタマイズされた現場アプリ エクスペリエンスのアプリは、アプリのセットアップ ポリシーで既に定義されており、機能はオンになっています。 |アプリは、カスタマイズされたアプリの一覧で定義された順序に基づいてピン留めされます。        |
|ユーザーは E、A、または G のライセンスを持っており、この機能は有効です。   | ユーザーは、カスタマイズされた現場アプリのエクスペリエンスを得られません。 現時点では、このエクスペリエンスは F ライセンスを持つユーザーにのみ適用されます。        |

> [!NOTE]
> カスタマイズされた現場アプリ エクスペリエンスでは、アプリやアプリの順序を変更することはできません。 現時点では、変更を加える場合は、独自のカスタム エクスペリエンスを設定できます。 これを行うには、まず機能をオフにします。 次に、[カスタム アプリ セットアップ ポリシーを作成](/microsoftteams/teams-app-setup-policies)し、[これをユーザーまたはグループに割り当てます](/microsoftteams/assign-policies-users-and-groups)。

## <a name="related-articles"></a>関連記事

- [Teams でトランシーバー アプリを管理する](/microsoftteams/walkie-talkie?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams で Tasks アプリを使用する](/microsoftteams/manage-tasks-app?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams でシフト アプリを使用する](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams で承認アプリを管理する](/microsoftteams/approval-admin?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
- [Teams でアプリのセットアップ ポリシーを管理する](/microsoftteams/teams-app-setup-policies)
- [Teams でアプリのアクセス許可ポリシーを管理する](/microsoftteams/teams-app-permission-policies)
