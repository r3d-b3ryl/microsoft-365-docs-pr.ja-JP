---
title: Microsoft 365 グループのゲスト アクセスを管理する
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Microsoft 365 グループにゲストを追加し、ゲスト ユーザーを表示し、PowerShell を使用してゲスト アクセスを制御する方法について説明します。
ms.openlocfilehash: 9a713684bb9a2401316dbb3289115be19b220cff
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453659"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Microsoft 365 グループのゲスト アクセスを管理する

既定では、組織の Microsoft 365 グループのゲスト アクセスが有効になっています。 管理者は、グループへのゲスト アクセスを、組織全体または個々のグループに対して許可するかを制御できます。

オンにすると、グループ メンバーは Outlook on Web を介して Microsoft 365 グループにゲスト ユーザーを招待できます。 招待状が承認のためにグループの所有者に送信されます。

承認が完了すると、ゲスト ユーザーがディレクトリとグループに追加されます。

> [!Note]
> ネイティブ モードまたは [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) にある Yammer Enterprise ネットワークは、ネットワークのゲストをサポートしていません。
> Microsoft 365 Connected Yammerグループは現在、ゲスト アクセスをサポートしていないが、ネットワーク内に接続されていない外部グループYammerできます。 手順については。「[Yammer の外部グループを作成して管理する](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups)」を参照してください。

グループ内のゲスト アクセスは、SharePoint や Teams を含む広範囲のシナリオの一部としてよく使用されます。 これらのサービスには、独自のゲスト共有設定があります。 グループ、SharePoint、Teams 間でゲスト共有をセットアップするための詳細な手順については、次を参照してください。

- [サイトでゲストと共同で作業する](../../solutions/collaborate-in-site.md)
- [チームでゲストと共同で作業する](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>グループのゲスト アクセスを管理する

グループのゲスト アクセスを有効または無効にするには、Microsoft 365 管理センターで行うことができます。

1. 管理センターで、[すべての設定組織の設定を表示する] に移動し、[サービス] タブで \>  \> **[Microsoft 365** グループ] を選択します。 
  
2. **[Microsoft 365 グループ**] ページで、組織外のユーザーがグループ リソースにアクセスできるかどうか、またはグループ所有者が組織外のユーザーをグループに追加するかどうかを選択します。

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>管理センターから Microsoft 365 グループにゲストを追加する

ゲストが既に自分のディレクトリ内にある場合、Microsoft 365 管理センターで、それらのゲストをグループに追加できます。 (動的メンバーシップを持つグループは [、Azure Active Directory で管理する必要があります](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule)。)
  
1. 管理センターで、[**グループ**]  >  [**グループ**] ページに移動します。
  
2. ゲストを追加するグループをクリックし、[メンバー] **タブで** [すべて表示してメンバーを管理する] **を選択** します。 
  
4. [**メンバーを追加**] を選択し、追加するゲストの名前を選択します。
    
5. [**保存**] を選択します。

ディレクトリに直接ゲストを追加する場合は、[Azure Portal で Azure Active Directory B2B コラボレーション ユーザーを追加する](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)ことができます。

ゲストの情報を編集する必要がある場合は、[Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ことができます。

## <a name="see-also"></a>関連項目

[特定のグループに対してゲスト ユーザーをブロックする](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Microsoft 365 管理センターでグループ メンバーシップを管理する](add-or-remove-members-from-groups.md)
  
[Azure Active Directory アクセス レビュー](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
