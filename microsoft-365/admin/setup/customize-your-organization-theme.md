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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: 'Microsoft 365 の既定のテーマを変更し、会社のロゴや色に合わせてカスタマイズする方法について説明します。 '
ms.openlocfilehash: b7a0b142b8bd465a9e3258aaaeb951b72bc53fc7
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52060936"
---
# <a name="customize-the-microsoft-365-theme-for-your-organization"></a>組織の Microsoft 365 テーマをカスタマイズする

組織の管理者は、組織内のユーザーに対して複数のテーマを作成し、組織の異なるメンバーに適用するテーマを選択できます。 組織のテーマは、組織内のユーザーのトップ ナビゲーション バーに表示されるテーマです。

組織内のすべてのユーザーに適用される既定のテーマを追加または更新できます。また、複数の Microsoft 365 グループに割り当て可能な最大 4 つのグループ テーマを作成することもできます。
  
## <a name="add-or-update-your-organizations-theme"></a>組織のテーマを追加または更新する

1. 管理センターで、[設定] [組織 **の設定]** ページ \> **に移動** し、[組織プロファイル] **タブを選択** します。

2. [組織プロファイル **] タブで** 、[組織のテーマ] **を選択します**。

すべてのテーマは、次のタブを使用してカスタマイズできます。

|**Tab**|**What can you do?**|
|:-----|:-----|
|[全般](#general-modify-a-theme) <br/> |テーマ名を変更し、最大 5 つのグループに割り当てる (該当する場合)。  <br/> |
|[ロゴ](#logos-specify-your-theme-logos) <br/> |暗いテーマやモバイル オプションOfficeテーマ ロゴを追加します。  <br/> |
|[Colors](#colors-choose-theme-colors) <br/> |ナビゲーション バー、アクセント、テキスト、アイコンの色を指定して配色をカスタマイズします。 <br/> |

## <a name="general-modify-a-theme"></a>全般: テーマを変更する

[全般] タブでのエクスペリエンスは、既定のテーマまたはグループ テーマを追加または変更するかどうかによって異なります。

### <a name="update-the-default-theme"></a>既定のテーマを更新する

既定のテーマは、最初に表示されるテーマです。  

1. 組織のテーマを以前にカスタマイズした場合は、[既定のテーマ] を選択して保存したカスタマイズのいずれかを使用するか、[テーマの追加]**を選択します**。
2. [全般 **] ページ** では、ユーザーがテーマを上書きし、ユーザーの表示名を表示できます。
3. **[保存]** を選択し、変更内容を保存します。  

> [!IMPORTANT]
> 既定のテーマは一意であり、名前を変更したり、組織内のすべてのユーザーに適用したりできない。 既定のテーマを削除するには、最初に他のすべてのテーマを削除する必要があります。

:::image type="content" source="../../media/default-theme-general.png" alt-text="スクリーンショット: 組織の既定のテーマを示す [全般] タブ":::

### <a name="create-a-group-theme"></a>グループ テーマの作成

最大 4 つの追加のグループ テーマを作成できます。

1. [全般 **] ページ** で、テーマの名前を入力します。

2. [ **グループ]** で、既定のテーマを使用する代わりに、グループテーマを表示できる最大 5 つの Microsoft 365 グループを選択できます。 また、ユーザーがテーマを上書きし、ユーザーの表示名を表示するのを防ぐことも可能です。

3. **[保存]** を選択します。

:::image type="content" source="../../media/default-theme-general-users.png" alt-text="スクリーンショット: 組織内のユーザーグループの既定のテーマを示す [全般] タブ":::

## <a name="logos-specify-your-theme-logos"></a>ロゴ: テーマのロゴを指定する

[ロゴ **] ページ** では、ロゴを追加し、ユーザーがロゴを選択するときに移動する URL を指定できます。

- **既定のロゴ**: ロゴをポイントする URL の場所を追加します。 URL で HTTPS が使用され、イメージが 200 x 30 ピクセル以上である必要があります。 既定のロゴは、JPG、PNG、GIF、または SVG 形式で指定できます。
- **代替ロゴ**: ロゴをポイントする URL の場所を追加します。 代替ロゴは、暗いテーマで使用Officeする必要があります。 既定のロゴと同じ要件。
- **小さな既定のロゴ**: ロゴをポイントする URL の場所を追加します。 画像は 48 x 48 ピクセル以上である必要があります。 このイメージは、小さいデバイスやモバイル デバイスに収まるサイズに調整できます。
- **小さな代替ロゴ**: ロゴをポイントする URL の場所を追加します。 このイメージには、小さな既定のロゴと同じ要件があります。
- **[オンクリック] リンク**: ロゴをポイントする URL の場所を追加します。 ロゴは、会社の Web サイトなど、任意の会社リソースへのリンクとして使用できます。

**[保存]** を選択し、変更内容を保存します。

ロゴは、いつでも削除できます。 [ロゴ] ページに戻 **り、[** 削除] を **選択します**。

:::image type="content" source="../../media/default-theme-logos.png" alt-text="スクリーンショット: 組織の既定のテーマ ロゴを示す [ロゴ] タブ":::

> [!NOTE]
> 既定では、ほとんどの組織で使用されるロゴの選択が最初に表示されます。 すべてのロゴ選択を表示するには、リストの下部に移動し、[詳細オプションを表示] **を選択します**。
  
## <a name="colors-choose-theme-colors"></a>色: テーマの色を選択する

[色 **] ページ** で、既定の色を設定し、使用するロゴを選択できます。

- **ナビゲーション バーの色**: ナビゲーション バーの背景に使用する色を選択します。 ナビゲーション バーは、すべてのページの上部に表示されます。
- **テキストとアイコンの色**: 上部ナビゲーション バーのテキストとアイコンに使用する色を選択します。
- **アクセントの色**: 白または明るい背景によく表示される色を選択します。 アクセントカラーは、白または明るい背景に表示されるいくつかのリンクやボタンの色を付けするために使用されます。 たとえば、アクセントの色は、ユーザーの受信トレイ内の要素と、ユーザーのポータル ページの要素 Office.com 使用されます。
- **[色のリセット**] : 色を既定の色にリセットするには、このリンクを選択します。
- **使用するロゴ:** 既定のロゴまたは自分で作成した他のロゴを選択します。

:::image type="content" source="../../media/default-theme-colors.png" alt-text="スクリーンショット: 組織の既定のテーマの色を示す [色] タブ":::

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="my-organization-already-has-a-theme-for-all-employees-how-will-this-change"></a>組織には、すべての従業員のテーマが既に設定されています。 この変更方法

既定のテーマは、引き続きすべての従業員に表示されます。新しいグループ テーマを追加すると、そのテーマに関連付けられた Microsoft 365 グループでのみ使用できます。

### <a name="whydont-isee-group-themes-in-the-admin-center"></a>管理センターにグループテーマが表示されるのがどうしてですか?

会社のテーマをカスタマイズできるのは、グローバル管理者のみです。グローバル リーダーには読み取り専用アクセス権があります。

### <a name="how-many-different-themes-can-i-set-up-for-my-organization"></a>組織に対して設定できるテーマの数  

最大 5 つのテーマを作成できます。 既定のテーマと 4 つのグループ テーマ。  

### <a name="can-i-use-security-groups-or-distribution-groups-instead-of-microsoft-365-groups"></a>Microsoft 365 グループの代わりにセキュリティ グループまたは配布グループを使用できますか?

いいえ、新しいグループ テーマは、セキュリティ グループや配布グループではなく、1 つ以上の Microsoft 365 グループにマップする必要があります。

> [!NOTE]
> Outlook では、 [配布グループを Microsoft 365 グループに](../manage/upgrade-distribution-lists.md) 変換できます。

### <a name="can-imanually-assign-a-theme-independent-ofmicrosoft-365-groups"></a>Microsoft 365 グループに依存しないテーマを手動で割り当てできますか?  

いいえ、新しいグループ テーマは 1 つ以上の Microsoft 365 グループにマップする必要があります。 Microsoft 365 グループのメンバーであるユーザーは、そのグループに適用されるテーマを取得します。 管理センターの [設定グループ] に移動すると[、Microsoft 365](../create-groups/create-groups.md)グループに新しいメンバーを作成 ****   >  **** して追加できます。

### <a name="what-happens-if-a-user-is-assigned-to-multiple-group-themes"></a>ユーザーが複数のグループ テーマに割り当てられている場合は、どうなるでしょうか。  

複数のグループ テーマに割り当てられているユーザーには、既定のテーマが表示されます。  

### <a name="why-cant-i-delete-the-default-theme"></a>既定のテーマを削除できない理由  

既定のテーマは、すべてのグループ テーマが削除された後にのみ削除できます。 グループ テーマを削除する前に、すべてのグループ テーマを削除してください。

### <a name="why-am-i-receiving-an-error-message-every-time-i-uploadalogo-url"></a>ロゴ URL をアップロードする度にエラー メッセージが表示される理由。  

使用しているロゴが、パブリックアドレス指定可能な URL として指定されている必要があります。 ロゴを Azure Blob Storage または [SharePoint Online](/azure/storage/blobs/storage-upload-process-images?tabs=dotnet) を使用して Office 365 コンテンツ配信ネットワークにアップロードするには、 [次の手順を実行します](../../enterprise/use-microsoft-365-cdn-with-spo.md)。

### <a name="why-am-i-receiving-themessagedoesnt-meet-minimum-color-contrast-ratio-of-451"></a>"4.5:1 の最小色コントラスト比を満たしていない" というメッセージが表示される理由

テキスト、アイコン、またはボタンの色と背景色の推奨コントラスト比は 4.5:1 です。 この推奨事項を上書きしてテーマを保存できます。これは要件ではありません。

### <a name="if-i-define-a-theme-which-places-in-microsoft-365-will-this-be-used"></a>テーマを定義する場合、Microsoft 365 で使用される場所は何ですか?

すべてのテーマは、Microsoft 365 スイート ヘッダーの一部として、組織内のすべてのユーザーのトップ ナビゲーション バーに表示されます。  
  
## <a name="related-articles"></a>関連記事

[カスタム タイルをアプリ起動ツールに追加する](../manage/customize-the-app-launcher.md)

[管理者向け Microsoft 365 グループの概要](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups)