---
title: 組織のMicrosoft Whiteboardへのアクセスを有効にして管理する
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
description: Microsoft 365 管理センターで組織のMicrosoft Whiteboardを設定する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b84a49f51b60b1aab7ea2ee791dbcc2e47520c64
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2022
ms.locfileid: "66159938"
---
# <a name="enable-and-manage-access-to-microsoft-whiteboard-for-your-organization"></a>組織のMicrosoft Whiteboardへのアクセスを有効にして管理する

>[!NOTE]
> この記事は、ホワイトボードを使用するEnterpriseまたは教育機関に適用されます。 米国政府機関GCC High 環境については、「GCC [High 環境のMicrosoft Whiteboardへのアクセスを有効にして管理](enable-whiteboard-access-gcc-high.md)する」を参照してください。

Microsoft Whiteboardは、人、コンテンツ、アイデアが集まるビジュアル コラボレーション キャンバスです。 現在、Whiteboard は、Enterpriseおよび Education のお客様向けに Azure で実行されています。 ホワイトボードは、OneDrive for Businessの上で実行されるように切り替え中です。 この切り替えにより、多くの新機能が追加され、ホワイトボードの作成、共有、検出、管理をOfficeドキュメントと同じくらい簡単に行えます。

ホワイトボードは、該当するMicrosoft 365テナントに対して自動的に有効になります。 

ホワイトボードは、SOC 1、SOC 2、ISO 27001、HIPAA、EU モデル条項などのグローバル標準に準拠しています。 

Whiteboard には、次の管理者設定が必要です。

- ホワイトボードは、Microsoft 365 管理センターでグローバルに有効にする必要があります。

- このコマンドレットは<code>Set-SPOTenant -IsWBFluidEnabled</code>、[SharePoint Online PowerShell を](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)使用して有効にする必要があります。

>[!NOTE]
> OneDrive for Business ストレージのロールアウトが進行中です。 Microsoft 365 管理センターに移動すると、テナントが既にOneDrive for Businessに移行されている場合、OneDrive for Businessストレージをオプトインまたはオプトアウトするオプションは無効になります。

Whiteboard へのアクセスは、次の方法で制御できます。

- Microsoft 365 管理センターを使用して、テナント全体の Whiteboard を有効または無効にします。

- Teams会議ポリシーを使用して、会議で特定のユーザーのホワイトボードを表示または非表示にします。 Web、ネイティブ クライアント、およびTeams タブ アプリを介して引き続き表示されます。

- Azure Active Directory管理センターを使用して Whiteboard にアクセスするには、条件付きアクセス ポリシーが必要です。

>[!NOTE]
> 会議ポリシー Teams、ホワイトボードのエントリ ポイントのみが非表示になります。ユーザーがホワイトボードを使用することを妨げるわけではありません。 条件付きアクセス ポリシーを使用すると、Whiteboard へのアクセスは禁止されますが、エントリ ポイントは非表示になりません。

## <a name="enable-or-disable-whiteboard"></a>ホワイトボードを有効または無効にする

テナントの Whiteboard を有効または無効にするには、次の手順に従います。

1. Microsoft 365 管理センターに移動します。

2. 管理センターのホーム ページの右上の [検索] ボックスに「ホワイトボード」と入力 *します*。

3. 検索結果で、[ **ホワイトボードの設定**] を選択します。

4. ホワイトボード パネルで、**組織全体のホワイトボードをオンまたはオフ** に切り替 **えます。**

5. **[保存]** を選択します。

6. [オンライン PowerShell をSharePointするConnect](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

7. 次 <code>Set-SPOTenant</code> のコマンドレットを使用して Fluid を有効にします。

   <pre><code class="lang-powershell">Set-SPOTenant -IsWBFluidEnabled $true</code></pre>
 
## <a name="show-or-hide-whiteboard"></a>ホワイトボードを表示または非表示にする

会議でホワイトボードを表示または非表示にするには、「 [会議ポリシーの設定](/microsoftteams/meeting-policies-content-sharing)」を参照してください。 

## <a name="prevent-access-to-whiteboard"></a>ホワイトボードへのアクセスを禁止する

特定のユーザーに対して Whiteboard にアクセスできないようにするには、 [条件付きアクセス ポリシーの構築に関するページを](/azure/active-directory/conditional-access/concept-conditional-access-policies)参照してください。

## <a name="see-also"></a>関連項目

[Whiteboard のデータを管理する](manage-data-organizations.md)

[ホワイトボードの共有を管理する](manage-sharing-organizations.md)

[Windowsにホワイトボードをデプロイする](deploy-on-windows-organizations.md)
