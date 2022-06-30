---
title: GCC High 環境向けの Microsoft Whiteboard へのアクセスを管理する
ms.author: chucked
author: chuckedmonson
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Whiteboard データを有効、無効、管理する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3521d1cb7bafcb5f863f3902d2f54f96a30975cd
ms.sourcegitcommit: bc35c7826e3403f259725ac72cca5bafd36aa56a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2022
ms.locfileid: "66554608"
---
# <a name="manage-access-to-microsoft-whiteboard-for-gcc-high-environments"></a>GCC High 環境向けの Microsoft Whiteboard へのアクセスを管理する

>[!NOTE]
> このガイダンスは、米国政府機関コミュニティ クラウド (GCC) の High 環境に適用されます。

OneDrive for Businessの Microsoft Whiteboard は、該当する Microsoft 365 テナントに対して既定で有効になっています。 テナント全体のレベルで有効または無効にすることができます。 **また、Azure Active Directory 管理センター** > **の Enterprise アプリケーション** で **Microsoft Whiteboard Services** が有効になっていることを確認する必要もあります。

次の URL が必要です。

- 'https://*.office365.us/'
- 'https://login.microsoftonline.us/'
- 'https://graph.microsoft.us/'
- 'https://graph.microsoftazure.us/'
- 'https://admin.onedrive.us'
- 'https://shell.cdn.office.net/'
- 'https://config.ecs.gov.teams.microsoft.us'
- 'https://tb.events.data.microsoft.com/'

Whiteboard へのアクセスは、次の方法で制御できます。

- [SharePoint Online PowerShell モジュール](/microsoft-365/enterprise/manage-sharepoint-online-with-microsoft-365-powershell)を使用して、テナント全体のホワイトボードを有効または無効にします。

- Teams 会議ポリシーを使用して、会議内の特定のユーザーのホワイトボードを表示または非表示にします。 Web、ネイティブ クライアント、Teams タブ アプリを介して引き続き表示されます。

- Azure Active Directory 管理センターを使用して Whiteboard にアクセスするには、条件付きアクセス ポリシーが必要です。

>[!NOTE]
> OneDrive for BusinessのホワイトボードはMicrosoft 365 管理センターに表示されません。 Teams 会議ポリシーでは、ホワイトボードのエントリ ポイントのみが非表示になり、ユーザーがホワイトボードを使用できなくなります。 条件付きアクセス策略は Whiteboard へのアクセスを禁止しますが、エントリ ポイントは非表示にしません。

## <a name="enable-or-disable-whiteboard"></a>ホワイトボードを有効または無効にする

テナントの Whiteboard を有効または無効にするには、次の手順に従います。 

1. [SharePoint Online PowerShell モジュール](/microsoft-365/enterprise/manage-sharepoint-online-with-microsoft-365-powershell)を使用して、Microsoft 365 テナント全体ですべての Fluid Experiences を有効または無効にします。

2. [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) に接続します。

3. 次 <code>Set-SPOTenant</code> のコマンドレットを使用して Fluid を有効にします。

   <pre><code class="lang-powershell">Set-SPOTenant -IsWBFluidEnabled $true</code></pre>

この変更は、テナント全体に適用されるまでに約 60 分かかります。 このオプションが表示されない場合は、モジュールを更新する必要があります。

>[!NOTE]
> 既定では、Whiteboard は有効になっています。 Azure Active Directory エンタープライズ アプリケーションで無効になっている場合、OneDrive for Businessのホワイトボードは機能しません。

## <a name="show-or-hide-whiteboard"></a>ホワイトボードを表示または非表示にする

会議でホワイトボードを表示または非表示にするには、「 [会議ポリシーの設定](/microsoftteams/meeting-policies-content-sharing)」を参照してください。

## <a name="see-also"></a>関連項目

[Whiteboard のデータを管理する - GCC High](manage-data-gcc-high.md)

[Whiteboard の共有を管理する - GCC High](manage-sharing-gcc-high.md)

[Whiteboard のクライアントを管理する - GCC High](manage-clients-gcc-high.md)




