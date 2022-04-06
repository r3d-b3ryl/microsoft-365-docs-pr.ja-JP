---
title: Microsoft 365 グループでのゲスト アクセスを管理する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: ゲストをグループに追加し、Microsoft 365表示し、PowerShell を使用してゲスト アクセスを制御する方法について説明します。
ms.openlocfilehash: ea5986c4b9e0c5124abc581f9ed35391e0885633
ms.sourcegitcommit: 7aa2441c1f2cc5b4b5495d6fdb993e563f86647f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64637942"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Microsoft 365 グループでのゲスト アクセスを管理する

既定では、組織Microsoft 365グループのゲスト アクセスが有効になっています。 管理者は、グループへのゲスト アクセスを、組織全体または個々のグループに対して許可するかを制御できます。

オンにすると、グループ メンバーは Web 上のユーザーを通じてMicrosoft 365グループOutlook招待できます。 招待状が承認のためにグループの所有者に送信されます。

承認されると、ゲストはディレクトリとグループに追加されます。

> [!Note]
> ネイティブ モードまたは [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) にある Yammer Enterprise ネットワークは、ネットワークのゲストをサポートしていません。
> Microsoft 365接続Yammerグループは現在、ゲスト アクセスをサポートしていないが、接続されていない外部グループをネットワーク内にYammerできます。 手順については。「[Yammer の外部グループを作成して管理する](/yammer/work-with-external-users/create-and-manage-external-groups)」を参照してください。

グループ内のゲスト アクセスは、SharePoint や Teams を含む広範囲のシナリオの一部としてよく使用されます。 これらのサービスには、独自のゲスト共有設定があります。 グループ、SharePoint、Teams 間でゲスト共有をセットアップするための詳細な手順については、次を参照してください。

- [サイトでゲストと共同で作業する](../../solutions/collaborate-in-site.md)
- [チームでゲストと共同で作業する](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>グループのゲスト アクセスを管理する

グループでゲスト アクセスを有効または無効にする場合は、[グループ] で有効または無効 <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**にできます**</a>。

1. 管理センターで、[組織の設定設定\>**を** 表示する] に移動し **、[**\>サービス] タブで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">組織の設定</a>] **をMicrosoft 365 グループ**。
  
2. [組織の **Microsoft 365 グループ**] ページで、組織外のユーザーにグループ リソースへのアクセスを許可するか、グループ所有者が組織外のユーザーをグループに追加するかどうかを選択します。

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>管理センターからMicrosoft 365グループにゲストを追加する

ゲストが既にディレクトリに存在する場合は、そのディレクトリからグループに<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Microsoft 365 管理センター</a>。 (動的メンバーシップを持つグループは、Azure Active Directoryで管理[する](/azure/active-directory/enterprise-users/groups-create-rule)必要があります)。
  
1. 管理センターで、<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**GroupsGroups**</a> **に** > 移動します。
  
2. ゲストを追加するグループをクリックし、[メンバー **] タブで** [すべて表示してメンバーを管理する] **を選択** します。 
  
4. [**メンバーを追加**] を選択し、追加するゲストの名前を選択します。
    
5. [**保存**] を選択します。

ディレクトリに直接ゲストを追加する場合は、[Azure Portal で Azure Active Directory B2B コラボレーション ユーザーを追加する](/azure/active-directory/b2b/add-users-administrator)ことができます。

ゲストの情報を編集する必要がある場合は、[Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ことができます。

## <a name="related-content"></a>関連コンテンツ

[特定のグループからのゲストをブロック](../../solutions/per-group-guest-access.md) する (記事)\
[グループ メンバーシップを管理する (Microsoft 365 管理センター](add-or-remove-members-from-groups.md))\
[Azure Active Directoryレビュー (](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)記事)\
[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (記事)
