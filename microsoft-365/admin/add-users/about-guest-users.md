---
title: Microsoft 365 管理センターのゲスト ユーザー
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: ゲストが会議に出席したり、招待されたTeamsでドキュメントを表示したり、チャットしたりできるように、Microsoft 365 管理センターでゲスト ユーザーリストを設定する方法について説明します。
ms.openlocfilehash: 5677492ca8607fd3034b62264897d397e1e65f32
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65466880"
---
# <a name="guest-users-in-microsoft-365-admin-center"></a>Microsoft 365 管理センターのゲスト ユーザー

Microsoft Teams、SharePoint、またはAzure Active Directoryに追加したゲストも <a href="https://go.microsoft.com/fwlink/p/?linkid=2074830" target="_blank">、Microsoft 365 管理センター</a>の **[ゲスト ユーザー**] 一覧に追加されます。 ゲストは、会議に出席したり、招待されたTeamsでドキュメントを表示したり、チャットしたりできます。
ユーザーが **ゲスト ユーザー** の一覧に表示されたら、そのユーザーのアクセス権を削除できます。

ゲスト ユーザーを表示するには、<a href="https://go.microsoft.com/fwlink/p/?linkid=2074830" target="_blank">Microsoft 365 管理センター</a>の左側のナビゲーションで [**ユーザー**] を展開し、[**ゲスト ユーザー**] を選択します。

## <a name="before-you-begin"></a>はじめに

このタスクを実行するには、グローバル管理者である必要があります。

## <a name="watch-add-guests-to-teams"></a>ウォッチ: Teamsにゲストを追加する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FQMp]

## <a name="watch-join-a-team-as-a-guest"></a>視聴: ゲストとしてチームに参加

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4tyys]

## <a name="steps-add-guests-in-azure-active-directory"></a>手順: Azure Active Directoryにゲストを追加する

Azure Active Directoryにゲストを追加するには、「[ゲスト ユーザーの追加](/azure/active-directory/b2b/b2b-quickstart-add-guest-users-portal)」を参照してください。

ユーザーを追加した後は、グループに割り当てたり、組織内のアプリへのアクセス権を付与したりすることもできます。 Azure AD portal でユーザーを追加すると、そのユーザーは <a href="https://go.microsoft.com/fwlink/p/?linkid=2074830" target="_blank">Microsoft 365 管理センター</a>の **[ゲスト ユーザー**] ページにも一覧表示されます。
**ユーザーをゲスト ユーザー** の一覧に追加した後、<a href="https://go.microsoft.com/fwlink/p/?linkid=2074830" target="_blank">Microsoft 365 管理センター</a>の [グループに追加](../create-groups/manage-guest-access-in-groups.md#add-guests-to-a-microsoft-365-group-from-the-admin-center)できます。

複数 [のゲストを](/azure/active-directory/b2b/tutorial-bulk-invite) 招待して組織との共同作業を行う場合は、ゲストを一括で追加する方法を参照してください。

## <a name="next-steps-remove-a-guest"></a>次の手順: ゲストを削除する

ゲスト ユーザーとの共同作業が完了したら、そのユーザーを削除でき、組織にアクセスできなくなります。

1. Microsoft 365 管理センターで [**ユーザー**] を展開し、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2074830" target="_blank">**ゲスト ユーザー**</a>] を選択します。
1. [ **ゲスト ユーザー** ] ページで、削除するユーザーを選択し、[ **ユーザーの削除**] を選択します。

Azure AD ポータルでユーザーを削除するには、「 [ゲスト ユーザーとリソースを削除する](/azure/active-directory/b2b/b2b-quickstart-add-guest-users-portal#clean-up-resources)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 管理センターのゲスト ユーザー](about-guest-users.md)

[ゲストが特定の Microsoft 365 グループまたは Microsoft teams チームに追加されないようにする](../../solutions/per-group-guest-access.md)
