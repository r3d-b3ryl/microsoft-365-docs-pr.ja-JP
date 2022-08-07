---
title: Microsoft 365 グループでのゲスト アクセスを管理する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
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
description: Microsoft 365 グループにゲストを追加し、ゲストを表示し、PowerShell を使用してゲスト アクセスを制御する方法について説明します。
ms.openlocfilehash: c2545c4b6e0d87f3f143139887ff50126bf41d06
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67274750"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Microsoft 365 グループでのゲスト アクセスを管理する

既定では、組織で Microsoft 365 グループのゲスト アクセスが有効になっています。 管理者は、グループへのゲスト アクセスを、組織全体または個々のグループに対して許可するかを制御できます。

オンにすると、グループ メンバーは Outlook on Web を使用して Microsoft 365 グループにゲストを招待できます。 招待状が承認のためにグループの所有者に送信されます。

承認されると、ゲストがディレクトリとグループに追加されます。

> [!Note]
> ネイティブ モードまたは [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) にある Yammer Enterprise ネットワークは、ネットワークのゲストをサポートしていません。
> Microsoft 365 接続 Yammer グループは現在、ゲスト アクセスをサポートしていませんが、Yammer ネットワークに接続されていない外部グループを作成できます。 手順については。「[Yammer の外部グループを作成して管理する](/yammer/work-with-external-users/create-and-manage-external-groups)」を参照してください。

グループ内のゲスト アクセスは、SharePoint や Teams を含む広範囲のシナリオの一部としてよく使用されます。 これらのサービスには、独自のゲスト共有設定があります。 グループ、SharePoint、Teams 間でゲスト共有をセットアップするための詳細な手順については、次を参照してください。

- [サイトでゲストと共同で作業する](../../solutions/collaborate-in-site.md)
- [チームでゲストと共同で作業する](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>グループのゲスト アクセスを管理する

グループ内のゲスト アクセスを有効または無効にする場合は、グループで行 <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**うことができます。**</a>

1. 管理センターで、[**すべての**\>設定 **組織の設定** を表示 **する]** \> に移動し <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">、[**サービス**] タブ</a>で **[Microsoft 365 グループ**] を選択します。
  
2. **[Microsoft 365 グループ**] ページで、組織外のユーザーにグループ リソースへのアクセスを許可するか、グループ所有者が組織外のユーザーをグループに追加するかを選択します。

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>管理センターから Microsoft 365 グループにゲストを追加する

ディレクトリにゲストが既に存在する場合は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Microsoft 365 管理センター</a>からグループに追加できます。 (動的メンバーシップを持つグループは [、Azure Active Directory で管理](/azure/active-directory/enterprise-users/groups-create-rule)する必要があります)。
  
1. 管理センターで、**グループ** >  グループに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**します**</a>。
  
2. ゲストを追加するグループを選択し、[**メンバー**] タブで [**すべてのメンバーの表示と管理**] を選択します。 
  
3. [**メンバーを追加**] を選択し、追加するゲストの名前を選択します。

4. [**保存**] を選択します。

ディレクトリに直接ゲストを追加する場合は、[Azure Portal で Azure Active Directory B2B コラボレーション ユーザーを追加する](/azure/active-directory/b2b/add-users-administrator)ことができます。

ゲストの情報を編集する必要がある場合は、[Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ことができます。

## <a name="remove-a-guest"></a>ゲストを削除する

ゲスト ユーザーとの共同作業が完了したら、それらを削除でき、組織にアクセスできなくなります。

1. Microsoft 365 管理センターで [**ユーザー**] を展開し、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2074830" target="_blank">**ゲスト ユーザー**</a>] を選択します。
1. [ **ゲスト ユーザー** ] ページで、削除するユーザーを選択し、[ **ユーザーの削除**] を選択します。

Azure AD ポータルでユーザーを削除するには、「 [ゲスト ユーザーとリソースを削除する](/azure/active-directory/b2b/b2b-quickstart-add-guest-users-portal#clean-up-resources)」を参照してください。


## <a name="related-content"></a>関連コンテンツ

[特定のグループからのゲストをブロックする](../../solutions/per-group-guest-access.md) (記事)\
[Microsoft 365 管理センターでグループ メンバーシップを管理する](add-or-remove-members-from-groups.md) (記事)\
[Azure Active Directory アクセス レビュー](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (記事)\
[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (記事)
