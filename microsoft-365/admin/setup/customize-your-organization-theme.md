---
title: 組織のテーマをカスタマイズする
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
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
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: Microsoft 365のナビゲーション バーの上部の既定のテーマを変更し、会社のロゴや色に合わせてカスタマイズする方法について説明します。
ms.openlocfilehash: 263f6e91fb995daa61fe220a94b6948c6f782400
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783053"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>組織のMicrosoft 365テーマをカスタマイズする

組織の管理者は、組織内のユーザーに対して複数のテーマを作成し、組織のさまざまなメンバーに適用するテーマを選択できます。 組織のテーマは、組織内のユーザーの上部ナビゲーション バーに表示されます。

組織内のすべてのユーザーに適用される既定のテーマを追加または更新できます。また、複数のMicrosoft 365 グループに割り当てることができる最大 4 つの追加のグループ テーマを作成することもできます。
  
## <a name="add-or-update-your-organizations-theme"></a>組織のテーマを追加または更新する

1. 管理センターで、[**設定** \> **組織設定**] ページに移動し、[**組織プロファイル**] タブを選択します。

2. [ **組織プロファイル** ] タブで、[ **カスタム テーマ**] を選択します。

すべての組織テーマは、次のタブを使用してカスタマイズできます。

|Tab|What can you do?|
|---|---|
|[全般](#general-modify-a-theme)|テーマ名を変更し、最大 5 つのグループに割り当てます (該当する場合)。|
|[ロゴ](#logos-specify-your-theme-logos)|ダーク テーマの代替ロゴを含め、組織のロゴを追加します。|
|[Colors](#colors-choose-theme-colors)|ナビゲーション バー、アクセント、テキスト、アイコンの色を指定して配色をカスタマイズします。|

## <a name="general-modify-a-theme"></a>全般: テーマを変更する

[全般] タブでのエクスペリエンスは、既定のテーマとグループ テーマのどちらを追加するか変更するかによって異なります。

### <a name="update-the-default-theme"></a>既定のテーマを更新する

既定のテーマは、最初に表示されるテーマです。  

1. 組織のテーマを以前にカスタマイズした場合は、[ **既定のテーマ** ] を選択し、保存したカスタマイズのいずれかを使用するか、[ **テーマの追加**] を選択します。
2. [ **全般** ] ページでは、ユーザーがテーマをオーバーライドできないようにし、ユーザーの表示名を表示できます。
3. **[保存]** を選択し、変更内容を保存します。  

> [!IMPORTANT]
> 既定のテーマは一意であり、名前を変更できず、組織内のすべてのユーザーに適用されます。 既定のテーマを削除するには、最初に他のすべてのテーマを削除する必要があります。

:::image type="content" source="../../media/Default_Theme_Panel1.png" alt-text="スクリーンショット: 組織の既定のテーマを示す [全般] タブ":::

### <a name="create-a-group-theme"></a>グループ テーマを作成する

最大 4 つの追加グループ テーマを作成できます。

1. [ **全般]** ページで、新しいテーマの名前を入力します。

2. [**グループ]** で、既定のテーマを使用する代わりに、グループ テーマを表示できる最大 5 つのMicrosoft 365 グループを選択できます。 また、ユーザーがテーマをオーバーライドしたり、ユーザーの表示名を表示したりできないようにすることもできます。

3. **[保存]** を選択します。

:::image type="content" source="../../media/default-theme-general-users1.png" alt-text="スクリーンショット: 組織内のユーザー グループの既定のテーマを示す [全般] タブ":::

## <a name="logos-specify-your-theme-logos"></a>ロゴ: テーマ ロゴを指定する

**[ロゴ**] ページでは、ロゴを追加し、ユーザーがロゴを選択したときに移動する URL を指定できます。

- **既定のロゴ: ロゴ** を指す URL の場所を追加します。 URL で HTTPS が使用されていることを確認します。 匿名アクセスを許可し、認証を必要としない HTTPS イメージ URL を追加します。 既定のテーマでは、10 kb 未満のロゴ画像をアップロードすることもできます。 既定のロゴは、JPG、PNG、GIF、または SVG 形式にすることができます。 SVG イメージの場合、垂直方向に 24 ピクセルに収まるようにサイズが変更されます。 JPG、PNG、GIF イメージは、200 x 48 ピクセルに合わせてスケーリングされます。 ロゴの縦横比は常に保持されます。
- **代替ロゴ: ロゴ** を指す URL の場所を追加します。 代替ロゴは、暗いテーマで使用できるように最適化Office必要があります。 既定のロゴと同じ要件。
- **オンクリック リンク**: ロゴを指す URL の場所を追加します。 ロゴは、会社の Web サイトなど、任意の会社のリソースへのリンクとして使用できます。 ロゴの URL の場所を選択しない場合は、既定でOfficeホーム ページに設定されます。

**[保存]** を選択し、変更内容を保存します。

:::image type="content" source="../../media/Logos_Tab.png" alt-text="スクリーンショット: ロゴ オプションを示す [ロゴ] タブ":::

ロゴはいつでも削除できます。 **[ロゴ**] ページに戻り、[削除] を選択 **するだけです**。
  
## <a name="colors-choose-theme-colors"></a>色: テーマの色を選択する

[ **色]** ページでは、既定の色を設定し、使用するロゴを選択できます。

- **ナビゲーション バーの色: ナビゲーション バー** の背景に使用する色を選択します。 ナビゲーション バーは、すべてのページの上部に表示されます。
- **テキストとアイコンの色**: 上部のナビゲーション バーのテキストとアイコンに使用する色を選択します。
- **アクセントの色**: 白または明るい背景によく表示される色を選びます。 アクセントの色は、白または明るい背景に表示される一部のリンクとボタンに色を付けるために使用されます。 たとえば、アクセントカラーは、ユーザーの受信トレイとOffice.com ポータル ページの要素に色を付けるために使用されます。
- **色をリセット** する: 既定の色に色をリセットするには、このリンクを選択します。

:::image type="content" source="../../media/default-theme-colors1.png" alt-text="スクリーンショット: 組織の既定のテーマの色を示す [色] タブ":::

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="my-organization-already-has-a-theme-for-all-employees-how-will-this-change"></a>組織には、すべての従業員に対するテーマが既に設定されています。 この変更はどのように行われますか?

既定のテーマは引き続きすべての従業員に表示されます。 新しいグループ テーマの追加は、そのテーマに関連付けられているMicrosoft 365 グループでのみ使用できます。

### <a name="why-dont-i-see-group-themes-in-the-admin-center"></a>管理センターにグループ テーマが表示されないのはなぜですか?

会社のテーマをカスタマイズできるのは、グローバル管理者のみです。 グローバル リーダーには読み取り専用アクセス権があります。

### <a name="how-many-different-themes-can-i-set-up-for-my-organization"></a>組織に対して設定できるテーマはいくつですか?  

最大 5 つのテーマを作成できます。 既定のテーマと 4 つのグループ テーマ。  

### <a name="can-i-use-security-groups-or-distribution-groups-instead-of-microsoft-365-groups"></a>Microsoft 365 グループの代わりにセキュリティ グループまたは配布グループを使用できますか?

いいえ。新しいグループ テーマは、セキュリティ グループや配布グループではなく、1 つ以上のMicrosoft 365 グループにマップする必要があります。

> [!NOTE]
> [Outlookでは、配布グループをMicrosoft 365 グループ](../manage/upgrade-distribution-lists.md)に変換できます。

### <a name="can-i-manually-assign-a-theme-independent-of-microsoft-365-groups"></a>Microsoft 365 グループに依存しないテーマを手動で割り当てることはできますか?  

いいえ。新しいグループ テーマは、1 つ以上のMicrosoft 365 グループにマップする必要があります。 Microsoft 365 グループのメンバーであるユーザーは、そのグループに適用されたテーマを取得します。 管理センターの [設定Groups に移動すると、新しいメンバーを作成](../create-groups/create-groups.md)して **Microsoft 365** >  **グループ** に追加できます。

### <a name="what-happens-if-a-user-is-assigned-to-multiple-group-themes"></a>ユーザーが複数のグループ テーマに割り当てられている場合はどうなりますか?  

複数のグループ テーマに割り当てられているユーザーには、既定のテーマが表示されます。  

### <a name="why-cant-i-delete-the-default-theme"></a>既定のテーマを削除できないのはなぜですか?  

既定のテーマは、すべてのグループ テーマが削除された後にのみ削除できます。 グループ テーマを削除する前に、必ずすべてのグループ テーマを削除してください。

### <a name="why-am-i-receiving-an-error-message-every-time-i-upload-a-logo-url"></a>ロゴ URL をアップロードするたびにエラー メッセージが表示されるのはなぜですか。  

使用しているロゴがパブリックアドレス指定可能な URL として指定されていることを確認します。 SharePoint Online で[ロゴをAzure Blob Storage](/azure/storage/blobs/storage-upload-process-images?tabs=dotnet)またはOffice 365 Content Delivery Networkにアップロードするには[、次の](../../enterprise/use-microsoft-365-cdn-with-spo.md)手順に従います。

### <a name="why-am-i-receiving-the-message-doesnt-meet-minimum-color-contrast-ratio-of-451"></a>"4.5:1 の最小色コントラスト比を満たしていない" というメッセージが表示されるのはなぜですか?

テキスト、アイコン、またはボタンの色と背景色の間の推奨コントラスト比は 4.5:1 です。 この推奨事項をオーバーライドして、テーマを保存することはできますが、これは要件ではありません。

### <a name="if-i-define-a-theme-which-places-in-microsoft-365-will-this-be-used"></a>テーマを定義した場合、これを使用するMicrosoft 365の場所はどれですか?

すべてのテーマが、Microsoft 365 スイート ヘッダーの一部として組織内のすべてのユーザーの上部ナビゲーション バーに表示されます。  
  
## <a name="related-content"></a>関連コンテンツ

[[マイ アプリ] ページとアプリ起動ツールにカスタム タイルを追加](../manage/customize-the-app-launcher.md) する (記事)\
[管理者向けのMicrosoft 365 グループの概要](../create-groups/office-365-groups.md) (記事)
