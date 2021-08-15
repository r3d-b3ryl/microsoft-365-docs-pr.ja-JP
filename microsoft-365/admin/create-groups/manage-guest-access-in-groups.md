---
title: グループ内のゲスト アクセスMicrosoft 365する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: ゲストをグループに追加し、Microsoft 365ユーザーを表示し、PowerShell を使用してゲスト アクセスを制御する方法について説明します。
ms.openlocfilehash: dd29775aebc9b5a6434e7ce5bdbd46b6a874d548b6a82f61f2e525f51b638c27
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53826491"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>グループ内のゲスト アクセスMicrosoft 365する

既定では、組織Microsoft 365グループのゲスト アクセスが有効になっています。 管理者は、グループへのゲスト アクセスを、組織全体または個々のグループに対して許可するかを制御できます。

オンにすると、グループ メンバーは、Web 上のユーザーを通じて、Microsoft 365グループOutlook招待できます。 招待状が承認のためにグループの所有者に送信されます。

承認が完了すると、ゲスト ユーザーがディレクトリとグループに追加されます。

> [!Note]
> ネイティブ モードまたは [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) にある Yammer Enterprise ネットワークは、ネットワークのゲストをサポートしていません。
> Microsoft 365接続Yammerグループは現在、ゲスト アクセスをサポートしていないが、ネットワーク内に接続されていない外部グループをYammerできます。 手順については。「[Yammer の外部グループを作成して管理する](/yammer/work-with-external-users/create-and-manage-external-groups)」を参照してください。

グループ内のゲスト アクセスは、SharePoint や Teams を含む広範囲のシナリオの一部としてよく使用されます。 これらのサービスには、独自のゲスト共有設定があります。 グループ、SharePoint、Teams 間でゲスト共有をセットアップするための詳細な手順については、次を参照してください。

- [サイトでゲストと共同で作業する](../../solutions/collaborate-in-site.md)
- [チームでゲストと共同で作業する](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>グループのゲスト アクセスを管理する

グループのゲスト アクセスを有効または無効にするには、Microsoft 365 管理センターで行うことができます。

1. 管理センターで、[組織の設定設定を表示する] \> **に移動し、[** サービス] タブで [グループ] を \> **Microsoft 365します**。 
  
2. [グループ **Microsoft 365]** ページで、組織外のユーザーにグループ リソースへのアクセスを許可するか、グループ所有者が組織外のユーザーをグループに追加するかどうかを選択します。

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>管理センターからゲストMicrosoft 365グループに追加する

ゲストが既に自分のディレクトリ内にある場合、Microsoft 365 管理センターで、それらのゲストをグループに追加できます。 (動的メンバーシップを持つグループは、[グループ内](/azure/active-directory/enterprise-users/groups-create-rule)でAzure Active Directory必要があります。)
  
1. 管理センターで、[**グループ**]  >  [**グループ**] ページに移動します。
  
2. ゲストを追加するグループをクリックし、[メンバー] **タブで** [すべて表示してメンバーを管理する] **を選択** します。 
  
4. [**メンバーを追加**] を選択し、追加するゲストの名前を選択します。
    
5. [**保存**] を選択します。

ディレクトリに直接ゲストを追加する場合は、[Azure Portal で Azure Active Directory B2B コラボレーション ユーザーを追加する](/azure/active-directory/b2b/add-users-administrator)ことができます。

ゲストの情報を編集する必要がある場合は、[Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ことができます。

## <a name="related-content"></a>関連コンテンツ

[特定のグループからのゲスト ユーザーのブロック](../../solutions/per-group-guest-access.md) (記事)\
[グループ メンバーシップを管理するには、Microsoft 365 管理センター](add-or-remove-members-from-groups.md) (記事)\
[Azure Active Directoryアクセス レビュー](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (記事)\
[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (記事)