---
title: Microsoft 365 グループでゲスト アクセスを管理する
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
description: ゲストをMicrosoft 365グループに追加する方法、ゲスト ユーザーを表示する方法、PowerShell を使用してゲスト アクセスを制御する方法について説明します。
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571939"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Microsoft 365 グループでゲスト アクセスを管理する

既定では、Microsoft 365 グループのゲスト アクセスは、組織で有効になっています。 管理者は、グループへのゲスト アクセスを、組織全体または個々のグループに対して許可するかを制御できます。

オンにすると、グループ メンバーは Web 上のOutlookを通じて、ゲスト ユーザーをMicrosoft 365 グループに招待できます。 招待状が承認のためにグループの所有者に送信されます。

承認が完了すると、ゲスト ユーザーがディレクトリとグループに追加されます。

> [!Note]
> ネイティブ モードまたは [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) にある Yammer Enterprise ネットワークは、ネットワークのゲストをサポートしていません。
> Microsoft 365接続Yammerグループは現在ゲスト アクセスをサポートしていませんが、Yammer ネットワーク内に接続されていない外部グループを作成できます。 手順については。「[Yammer の外部グループを作成して管理する](/yammer/work-with-external-users/create-and-manage-external-groups)」を参照してください。

グループ内のゲスト アクセスは、SharePoint や Teams を含む広範囲のシナリオの一部としてよく使用されます。 これらのサービスには、独自のゲスト共有設定があります。 グループ、SharePoint、Teams 間でゲスト共有をセットアップするための詳細な手順については、次を参照してください。

- [サイトでゲストと共同で作業する](../../solutions/collaborate-in-site.md)
- [チームでゲストと共同で作業する](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>グループのゲスト アクセスを管理する

グループのゲスト アクセスを有効または無効にするには、Microsoft 365 管理センターで行うことができます。

1. 管理センターで \> **、[設定 組織** のすべての設定を表示] に移動 \> し、[**サービス**] タブで **[Microsoft 365 グループ**] を選択します。
  
2. [Microsoft 365 **グループ**] ページで、組織外のユーザーがグループ リソースにアクセスできるようにするか、組織外のユーザーをグループに追加するかを選択します。

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>管理センターからMicrosoft 365 グループにゲストを追加する

ゲストが既に自分のディレクトリ内にある場合、Microsoft 365 管理センターで、それらのゲストをグループに追加できます。 (動的メンバーシップを持つグループは[、Azure Active Directoryで管理](/azure/active-directory/enterprise-users/groups-create-rule)する必要があります。
  
1. 管理センターで、[**グループ**]  >  [**グループ**] ページに移動します。
  
2. ゲストを追加するグループをクリックし、[**メンバー** ] タブで [**すべてのメンバーの表示とメンバーの管理**] を選択します。 
  
4. [**メンバーを追加**] を選択し、追加するゲストの名前を選択します。
    
5. [**保存**] を選択します。

ディレクトリに直接ゲストを追加する場合は、[Azure Portal で Azure Active Directory B2B コラボレーション ユーザーを追加する](/azure/active-directory/b2b/add-users-administrator)ことができます。

ゲストの情報を編集する必要がある場合は、[Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ことができます。

## <a name="related-content"></a>関連コンテンツ

[特定のグループのゲスト ユーザーをブロック](../../solutions/per-group-guest-access.md) する (記事)

[Microsoft 365管理センターでのグループ メンバーシップの管理](add-or-remove-members-from-groups.md)(記事)
  
[Azure Active Directoryアクセスレビュー](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (記事)

[セット-AzureADUser](/powershell/module/azuread/set-azureaduser) (記事)