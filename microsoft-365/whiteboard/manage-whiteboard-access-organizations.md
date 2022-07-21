---
title: 組織の Microsoft Whiteboard へのアクセスを管理する
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
description: Microsoft 365 管理センターで組織の Microsoft Whiteboard を設定する方法について説明します。
ms.openlocfilehash: 3c75bbfe6b2babf130f8980fe627ec05a8b431e3
ms.sourcegitcommit: 24827a509b3e78959ce67679646e572a0c996282
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66917653"
---
# <a name="manage-access-to-microsoft-whiteboard-for-your-organization"></a>組織の Microsoft Whiteboard へのアクセスを管理する

>[!NOTE]
> この記事は、Whiteboard を使用するエンタープライズ組織または教育機関に適用されます。 米国政府機関の GCC High 環境については、「 [GCC High 環境用の Microsoft Whiteboard へのアクセスを管理する](manage-whiteboard-access-gcc-high.md)」を参照してください。

Microsoft Whiteboard は、人、コンテンツ、アイデアが集まるビジュアル コラボレーション キャンバスです。 現在、Whiteboard は Azure for Enterprise および Education のお客様で実行されています。 ホワイトボードは、OneDrive for Businessの上で実行されるように切り替え中です。 この移行により、多くの新機能が追加され、任意の Office ドキュメントと同じくらい簡単にホワイトボードを作成、共有、検出、管理できます。

ホワイトボードは、該当する Microsoft 365 テナントに対して自動的に有効になります。 

ホワイトボードは、SOC 1、SOC 2、ISO 27001、HIPAA、EU モデル条項などのグローバル標準に準拠しています。 

Whiteboard には、次の管理者設定が必要です。

- ホワイトボードは、Microsoft 365 管理センターでグローバルに有効にする必要があります。

- このコマンドレットは<code>Set-SPOTenant -IsWBFluidEnabled</code>[、SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) を使用して有効にする必要があります。

>[!NOTE]
> OneDrive for Business ストレージのロールアウトが進行中です。 Microsoft 365 管理センターに移動すると、テナントが既にOneDrive for Businessに移行されている場合、OneDrive for Businessストレージをオプトインまたはオプトアウトするオプションは無効になります。

Whiteboard へのアクセスは、次の方法で制御できます。

- Microsoft 365 管理センターを使用して、テナント全体の Whiteboard を有効または無効にします。

- Teams 会議ポリシーを使用して、会議内の特定のユーザーのホワイトボードを表示または非表示にします。 Web、ネイティブ クライアント、Teams タブ アプリを介して引き続き表示されます。

- Azure Active Directory 管理センターを使用して Whiteboard にアクセスするには、条件付きアクセス ポリシーが必要です。

>[!NOTE]
> Teams 会議ポリシーでは、ホワイトボードのエントリ ポイントのみが非表示になります。これにより、ユーザーが Whiteboard を使用できなくなります。 条件付きアクセス ポリシーを使用すると、Whiteboard へのアクセスは禁止されますが、エントリ ポイントは非表示になりません。

## <a name="enable-or-disable-whiteboard"></a>ホワイトボードを有効または無効にする

テナントの Whiteboard を有効または無効にするには、次の手順に従います。

1. Microsoft 365 管理センターに移動します。

2. 管理センターのホーム ページの右上の [検索] ボックスに「ホワイトボード」と入力 *します*。

3. 検索結果で、[ **ホワイトボードの設定**] を選択します。

4. ホワイトボード パネルで、**組織全体のホワイトボードをオンまたはオフ** に切り替 **えます。**

5. **[保存]** を選択します。

6. [SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) に接続します。

7. 次 <code>Set-SPOTenant</code> のコマンドレットを使用して Fluid を有効にします。

   <pre><code class="lang-powershell">Set-SPOTenant -IsWBFluidEnabled $true</code></pre>
 
## <a name="show-or-hide-whiteboard"></a>ホワイトボードを表示または非表示にする

会議でホワイトボードを表示または非表示にするには、「 [会議ポリシーの設定](/microsoftteams/meeting-policies-content-sharing)」を参照してください。 

## <a name="prevent-access-to-whiteboard"></a>ホワイトボードへのアクセスを禁止する

特定のユーザーに対して Whiteboard にアクセスできないようにするには、 [条件付きアクセス ポリシーの構築に関するページを](/azure/active-directory/conditional-access/concept-conditional-access-policies)参照してください。

## <a name="see-also"></a>関連項目

[Whiteboard のデータを管理する](manage-data-organizations.md)

[ホワイトボードの共有を管理する](manage-sharing-organizations.md)

[Windows にホワイトボードを展開する](deploy-on-windows-organizations.md)
